---
title: "Kod oluşturma, derleme ve adlandırma kuralları Microsoft Fakes | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20221de4-2a9e-4787-b99a-b5855bb90872
caps.latest.revision: "16"
ms.author: douge
manager: douge
ms.openlocfilehash: 34cfe9041a9e724136c9d7c5a19b1c74f2309b2a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="code-generation-compilation-and-naming-conventions-in-microsoft-fakes"></a>Microsoft Fakes'te kod oluşturma, derleme ve adlandırma kuralları
Bu konu, Fakes kodu oluşturma ve derleme seçenekleri ve sorunları açıklar ve oluşturulan Fakes türleri, üyeleri ve parametreleri için adlandırma kurallarını açıklar.  
  
 **Gereksinimler**  
  
-   Visual Studio Enterprise  
  
##  <a name="BKMK_In_this_topic"></a>Bu konudaki  
  
-   [Kod oluşturma ve derleme](#BKMK_Code_generation_and_compilation)  
  
-   [Kod oluşturma yer tutucular olarak yapılandırma](#BKMK_Configuring_code_generation_of_stubs)
  
-   [Tür filtreleme](#BKMK_Type_filtering)
  
-   [Stubbing somut sınıflar ve sanal yöntemler](#BKMK_Stubbing_concrete_classes_and_virtual_methods)
  
-   [İç türleri](#BKMK_Internal_types)
  
-   [Yapı kez en iyi duruma getirme](#BKMK_Optimizing_build_times)
  
-   [Derleme adı çakışan önleme](#BKMK_Avoiding_assembly_name_clashing)  
  
-   [Adlandırma kuralları fakes](#BKMK_Fakes_naming_conventions)  
  
-   [Adlandırma kuralları Dolgu türü ve saplama yazın](#BKMK_Shim_type_and_stub_type_naming_conventions)
  
-   [Adlandırma kuralları dolgusu temsilci özelliği veya saplama temsilci alan](#BKMK_Shim_delegate_property_or_stub_delegate_field_naming_conventions)
  
-   [Parametre türü adlandırma kuralları](#BKMK_Parameter_type_naming_conventions)
  
-   [Özyinelemeli kuralları](#BKMK_Recursive_rules)  
  
-   [Dış Kaynaklar](#BKMK_External_resources)  
  
-   [Kılavuzu](#BKMK_Guidance)  
  
##  <a name="BKMK_Code_generation_and_compilation"></a>Kod oluşturma ve derleme  
  
###  <a name="BKMK_Configuring_code_generation_of_stubs"></a>Kod oluşturma yer tutucular olarak yapılandırma  
 Saplama türlerini nesil .fakes dosya uzantılı bir XML dosyasında yapılandırılır. Fakes framework özel MSBuild görevleri aracılığıyla derleme işlemindeki tümleştirir ve bu dosyaların derleme zamanında algılar. Fakes kod oluşturucunun bir bütünleştirilmiş koda saplama türlerini derler ve projesine başvuru ekler.  
  
 Aşağıdaki örnek FileSystem.dll içinde tanımlanan saplama türleri gösterilmektedir:  
  
```xml  
<Fakes xmlns="http://schemas.microsoft.com/fakes/2011/">  
    <Assembly Name="FileSystem"/>  
</Fakes>  
  
```  
  
###  <a name="BKMK_Type_filtering"></a>Tür filtreleme  
 Filtreler .fakes dosyasında hangi tür tamamlanmamış kısıtlamak için ayarlanabilir. Sil, Ekle, Kaldır öğeleri seçili türlerinin bir listesini oluşturmak için StubGeneration öğesi altında sınırsız sayıda ekleyebilirsiniz.  
  
 Örneğin, bu .fakes dosya türleri için sistem ve System.IO ad altında yer tutucular oluşturur, ancak "İşlemek" sistemde içeren herhangi bir türü dışlar:  
  
```xml  
<Fakes xmlns="http://schemas.microsoft.com/fakes/2011/">  
  <Assembly Name="mscorlib" />  
  <!-- user code -->  
  <StubGeneration>  
    <Clear />  
    <Add Namespace="System!" />  
    <Add Namespace="System.IO!"/>  
    <Remove TypeName="Handle" />  
  </StubGeneration>  
  <!-- /user code -->  
</Fakes>  
```  
  
 Filtre dizeleri basit dilbilgisi eşleştirme nasıl yapılması gerektiğini tanımlamak için kullanın:  
  
-   Filtreleri, varsayılan olarak duyarsızdır; filtreler altdizgi eşleştirme gerçekleştirin:  
  
     `el`"hello" ile eşleşir  
  
-   Ekleme `!` filtre sonuna kadar kesin büyük küçük harfe duyarlı bir eşleşme hale getirir:  
  
     `el!`"hello" eşleşmiyor.  
  
     `hello!`"hello" ile eşleşir  
  
-   Ekleme `*` filtre sonuna kolaylaştırır önek dizesi eşleşen:  
  
     `el*`"hello" eşleşmiyor.  
  
     `he*`"hello" ile eşleşir  
  
-   Noktalı virgülle ayrılmış bir listede birden çok filtre bir ayrım birleştirilir:  
  
     `el;wo`"hello" ve "world" ile eşleşir  
  
###  <a name="BKMK_Stubbing_concrete_classes_and_virtual_methods"></a>Stubbing somut sınıflar ve sanal yöntemler  
 Varsayılan olarak, tüm korumalı olmayan sınıfları saplama türlerini üretilir. Soyut sınıflar .fakes yapılandırma dosyası için saplama türlerini kısıtlamaya mümkündür:  
  
```xml  
<Fakes xmlns="http://schemas.microsoft.com/fakes/2011/">  
  <Assembly Name="mscorlib" />  
  <!-- user code -->  
  <StubGeneration>  
    <Types>  
      <Clear />  
      <Add AbstractClasses="true"/>  
    </Types>  
  </StubGeneration>  
  <!-- /user code -->  
</Fakes>  
```  
  
###  <a name="BKMK_Internal_types"></a>İç türleri  
 Fakes Kod Oluşturucu dolgusu türleri oluşturmak ve oluşturulan Fakes derleme görünür türleri türlerinde saplama. İç türleri shimmed derlemenin Fakes ve test derlemenizi görünür hale getirmek için ekleme <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> öznitelikleri için oluşturulan Fakes derleme ve test derlemesinin görünürlük sağlar shimmed bütünleştirilmiş kodu. Örnek buradadır:  
  
```csharp  
// FileSystem\AssemblyInfo.cs  
[assembly: InternalsVisibleTo("FileSystem.Fakes")]  
[assembly: InternalsVisibleTo("FileSystem.Tests")]  
```  
  
 **Türü kesin adlandırılmış derlemelerde iç türleri**  
  
 Shimmed derleme güçlü olarak adlandırılmamış ve erişim iç türleri derlemenin istiyorsanız:  
  
-   Test derlemenizi ve Fakes derleme kesin adlandırılmış olmalıdır.  
  
-   Ortak anahtarlar Fakes derleme ve test eklemelisiniz **Internalsvisibletoattribute** shimmed derlemelerde öznitelikleri. Bizim örnek öznitelikleri shimmed bütünleştirilmiş kodda shimmed derleme güçlü olarak adlandırılmamış zaman nasıl görüneceği aşağıda verilmiştir:  
  
    ```csharp  
    // FileSystem\AssemblyInfo.cs  
    [assembly: InternalsVisibleTo("FileSystem.Fakes",  
        PublicKey=<Fakes_assembly_public_key>)]  
    [assembly: InternalsVisibleTo("FileSystem.Tests",  
        PublicKey=<Test_assembly_public_key>)]  
    ```  
  
 Shimmed derleme güçlü olarak adlandırılmamış, Fakes framework kesinlikle otomatik olarak oluşturulan Fakes derleme oturum. Strong test derlemeyi imzalamak gerekir. Bkz: [oluşturma ve tanımlayıcı adlı derlemeler kullanma](http://msdn.microsoft.com/Library/ffbf6d9e-4a88-4a8a-9645-4ce0ee1ee5f9).  
  
 Oluşturulan tüm derlemeleri eklemek için bir başlangıç noktası olarak bu parçacığı kullanabilmeniz için imzalamak için aynı anahtar Fakes framework kullanan **InternalsVisibleTo** shimmed derleme kodunuzu fakes derlemeye özniteliği.  
  
```csharp  
[assembly: InternalsVisibleTo("FileSystem.Fakes, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e92decb949446f688ab9f6973436c535bf50acd1fd580495aae3f875aa4e4f663ca77908c63b7f0996977cb98fcfdb35e05aa2c842002703cad835473caac5ef14107e3a7fae01120a96558785f48319f66daabc862872b2c53f5ac11fa335c0165e202b4c011334c7bc8f4c4e570cf255190f4e3e2cbc9137ca57cb687947bc")]  
```  
  
 Fakes derleme için farklı bir ortak anahtar belirtebilirsiniz, bir anahtar gibi tam yolunu belirterek shimmed derleme için oluşturdunuz **.snk** olarak alternatif anahtarı içeren dosya `KeyFile` öznitelik değeri `Fakes` \\ `Compilation` öğesinin **.fakes** dosya. Örneğin:  
  
```xml  
<-- FileSystem.Fakes.fakes -->  
<Fakes ...>  
  <Compilation KeyFile="full_path_to_the_alternate_snk_file" />  
</Fakes>  
  
```  
  
 Daha sonra diğer ortak anahtarını kullanmak zorunda **.snk** InternalVisibleTo özniteliğinin ikinci parametre olarak bir dosya shimmed bütünleştirilmiş kodu Fakes derlemede için:  
  
```csharp  
// FileSystem\AssemblyInfo.cs  
[assembly: InternalsVisibleTo("FileSystem.Fakes",  
    PublicKey=<Alternate_public_key>)]  
[assembly: InternalsVisibleTo("FileSystem.Tests",  
    PublicKey=<Test_assembly_public_key>)]  
```  
  
 Yukarıdaki değerleri örnekte `Alternate_public_key` ve `Test_assembly_public_key` aynı olabilir.  
  
###  <a name="BKMK_Optimizing_build_times"></a>Yapı kez en iyi duruma getirme  
 Derleme Fakes derlemelerin, derleme zamanı önemli ölçüde artırabilir. Üçüncü taraf derlemeler ve Fakes derlemeleri .NET sistem derlemeler için ayrı bir merkezi projesi oluşturarak yapı süresini en aza indirebilirsiniz. Bu tür derlemeler nadiren makinenizde değiştiğinden, diğer projeler oluşturulan Fakes derlemelerde yeniden kullanabilirsiniz.  
  
 Birim testi projelerini proje klasöründeki FakesAssemblies altına yerleştirilmiş derlenmiş Fakes derlemelerine başvuru yalnızca alabilir.  
  
1.  .NET çalışma zamanı sürümü test projelerinizi eşleşen yeni bir sınıf kitaplığı oluşturun. Şimdi Fakes.Prebuild çağırın. Class1.cs dosyası gerekli projeden kaldırın.  
  
2.  Tüm sistem ve üçüncü taraf derlemeleri Fakes için gereken başvuru ekleyin.  
  
3.  Her derlemeler için .fakes dosyasını ekleyin ve oluşturun.  
  
4.  Test projenizden  
  
    -   DLL Fakes çalışma zamanı için bir başvuru olduğundan emin olun:  
  
         C:\Program Files\Microsoft Visual Studio 12.0\Common7\IDE\PublicAssemblies\Microsoft.QualityTools.Testing.Fakes.dll  
  
    -   İçin oluşturduğunuz her derlemesi için Fakes, projenizin Fakes.Prebuild\FakesAssemblies klasörüne karşılık gelen DLL dosyasının bir başvuru ekleyin.  
  
###  <a name="BKMK_Avoiding_assembly_name_clashing"></a>Derleme adı çakışan önleme  
 Bir ekip ortamında, tüm yapı çıkışları tek bir dizin birleştirilir. Birden çok proje Fakes kullanarak söz konusu olduğunda, farklı sürüm Fakes derlemelerden birbirlerini geçersiz olabilir. Örneğin, .NET Framework 2.0 mscorlib.dll TestProject1 fakes ve her ikisi de bir mscorlib verecek TestProject2 mscorlib.dll için .NET Framework 4 fakes. Fakes.dll Fakes derleme.  
  
 Bu sorunu önlemek için Fakes otomatik olarak tam sürüm Fakes derleme adları olmayan proje başvuruları için .fakes dosya eklenirken oluşturmanız gerekir. Fakes derleme adı oluşturduğunuzda sürümü tam Fakes derleme adının bir sürüm numarası katıştırır:  
  
 MyAssembly derleme ve sürüm 1.2.3.4 Fakes derleme MyAssembly.1.2.3.4.Fakes addır.  
  
 Değiştirme veya .fakes derleme öğesinde sürüm özniteliğini düzenleyerek bu sürümü kaldırın:  
  
```xml  
attribute of the Assembly element in the .fakes:  
<Fakes ...>  
  <Assembly Name="MyAssembly" Version="1.2.3.4" />  
  ...  
</Fakes>  
  
```  
  
##  <a name="BKMK_Fakes_naming_conventions"></a>Adlandırma kuralları fakes  
  
###  <a name="BKMK_Shim_type_and_stub_type_naming_conventions"></a>Adlandırma kuralları Dolgu türü ve saplama yazın  
 **Ad alanları**  
  
-   . Fakes soneki ad alanına eklenir.  
  
     Örneğin, `System.Fakes` ad alanı, sistem ad alanı dolgusu türlerini içerir.  
  
-   Global.Fakes boş ad alanı dolgusu türünü içerir.  
  
 **Tür adları**  
  
-   Dolgu önek Dolgu türü adı oluşturmak için tür adı eklenir.  
  
     Örneğin, ShimExample örnek türü dolgusu türüdür.  
  
-   Saplama önek saplama türü adı oluşturmak için tür adı eklenir.  
  
     Örneğin, StubIExample IExample türü saplama türüdür.  
  
 **Tür bağımsız değişkenleri ve iç içe geçmiş tür yapıları**  
  
-   Genel tür bağımsız değişkenleri kopyalanır.  
  
-   İç içe geçmiş tür yapısı dolgusu türleri için kopyalanır.  
  
###  <a name="BKMK_Shim_delegate_property_or_stub_delegate_field_naming_conventions"></a>Adlandırma kuralları dolgusu temsilci özelliği veya saplama temsilci alan  
 **Temel kurallar** adlandırma, boş bir ad başlatma alan için:  
  
-   Yöntem adı eklenir.  
  
-   Yöntem adı bir açık arabirim uygulaması ise, nokta kaldırılır.  
  
-   Yöntem genel, ise `Of`  *n*  burada eklenir  *n*  genel yöntem bağımsız değişkenlerin sayısı.  
  
 **Özel yöntem adları** özelliği gibi alıcı veya ayarlayıcılar aşağıdaki tabloda açıklandığı gibi değerlendirilir.  
  
|Yöntemi ise...|Örnek|Eklenen yöntem adı|  
|-------------------|-------------|--------------------------|  
|A **Oluşturucusu**|`.ctor`|`Constructor`|  
|Statik **Oluşturucusu**|`.cctor`|`StaticConstructor`|  
|Bir **erişimci** (örneğin, özellik alıcıları) "_" yöntemi ile ayrılmış iki bölümden oluşan ad|*kind_name* (ortak servis talebi ancak ECMA tarafından zorlanan)|*NameKind*, burada her iki bölümü büyük harfli takas ve|  
||Özellik alıcısı`Prop`|`PropGet`|  
||Özellik ayarlayıcı`Prop`|`PropSet`|  
||Olay ekleyici|`Add`|  
||Olay kaldırıcısını|`Remove`|  
|Bir **işleci** iki bölümden oluşur|`op_name`|`NameOp`|  
|Örneğin: + işleci|`op_Add`|`AddOp`|  
|İçin bir **dönüştürme işleci**, dönüş türü eklenir.|`T op_Implicit`|`ImplicitOpT`|  
  
 **Notlar**  
  
-   **Alıcılar ve ayarlayıcılar dizin oluşturucular,** özelliğine benzer şekilde işlenir. Bir dizin oluşturucu için varsayılan ad `Item`.  
  
-   **Parametre türü** adları dönüştürülen ve birleştirilmiş.  
  
-   **Dönüş türü** aşırı belirsizlik olmadıkça göz ardı edilir. Bu durumda, dönüş türü adının sonuna eklenir  
  
###  <a name="BKMK_Parameter_type_naming_conventions"></a>Parametre türü adlandırma kuralları  
  
|Verilen|Eklenen dizedir...|  
|-----------|-------------------------|  
|A **türü**`T`|T<br /><br /> Ad alanı, iç içe geçmiş yapısı ve genel ı eşleştir bırakılır.|  
|Bir **çıkış parametresi**`out T`|`TOut`|  
|A **ref parametresi**`ref T`|`TRef`|  
|Bir **dizi türü**`T[]`|`TArray`|  
|A **çok boyutlu bir dizi** türü`T[ , , ]`|`T3`|  
|A **işaretçi** türü`T*`|`TPtr`|  
|A **genel tür**`T<R1, ...>`|`TOfR1`|  
|A **genel tür bağımsız değişkeni** `!i` türü`C<TType>`|`Ti`|  
|A **genel yöntem bağımsız değişkeni** `!!i` yöntemi`M<MMethod>`|`Mi`|  
|A **iç içe türü**`N.T`|`N`, ardından eklenir`T`|  
  
###  <a name="BKMK_Recursive_rules"></a>Özyinelemeli kuralları  
 Aşağıdaki kurallar uygulanan yinelemeli olarak şunlardır:  
  
-   Fakes kullandığı için C# Fakes derlemeleri oluşturma için geçersiz bir C# belirteci oluşturur herhangi bir karakter kaçışlı "_" (alt çizgi).  
  
-   Sonuçta elde edilen bir ad bildiri türü herhangi bir üyenin ile çakışıyor numaralandırma düzeni 01 ile başlayan iki basamaklı sayaç ekleyerek kullanılır.  
  
##  <a name="BKMK_External_resources"></a>Dış Kaynaklar  
  
###  <a name="BKMK_Guidance"></a>Kılavuzu  
 [Visual Studio 2012 - bölüm 2 ile sürekli teslimat için test etme: birim testi: iç test etme](http://go.microsoft.com/fwlink/?LinkID=255188)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft Fakes ile Test edilen kodu yalıtma](../test/isolating-code-under-test-with-microsoft-fakes.md)
