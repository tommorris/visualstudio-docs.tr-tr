---
title: Kod oluşturma, derleme ve Visual Studio için Microsoft Fakes adlandırma kuralları
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 93aec7e83ba5af9bab8da351624df861b46e475c
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36282112"
---
# <a name="code-generation-compilation-and-naming-conventions-in-microsoft-fakes"></a>Microsoft Fakes'te kod oluşturma, derleme ve adlandırma kuralları

Bu makalede, Fakes kodu oluşturma ve derleme seçenekleri ve konuları açıklanır ve oluşturulan Fakes türleri, üyeleri ve parametreleri için adlandırma kurallarını açıklar.

**Gereksinimler**

-   Visual Studio Enterprise
-   Bir .NET Framework projesi

> [!NOTE]
> .NET standart projeleri desteklenmez.

## <a name="code-generation-and-compilation"></a>Kod oluşturma ve derleme

### <a name="configure-code-generation-of-stubs"></a>Kod oluşturma yer tutucular olarak yapılandırın

Saplama türlerini nesil sahip bir XML dosyasında yapılandırılmış *.fakes* dosya uzantısı. Fakes framework özel MSBuild görevleri aracılığıyla derleme işlemindeki tümleştirir ve bu dosyaların derleme zamanında algılar. Fakes kod oluşturucunun bir bütünleştirilmiş koda saplama türlerini derler ve projesine başvuru ekler.

Aşağıdaki örnek tanımlanan saplama türleri gösterilmektedir *FileSystem.dll*:

```xml
<Fakes xmlns="http://schemas.microsoft.com/fakes/2011/">
    <Assembly Name="FileSystem"/>
</Fakes>
```

### <a name="type-filtering"></a>Tür filtreleme

Filtreler ayarlanabilir *.fakes* hangi tür tamamlanmamış kısıtlamak için dosya. Sil, Ekle, Kaldır öğeleri seçili türlerinin bir listesini oluşturmak için StubGeneration öğesi altında sınırsız sayıda ekleyebilirsiniz.

Örneğin, aşağıdaki *.fakes* dosya türleri için sistem ve System.IO ad altında yer tutucular oluşturur, ancak "İşlemek" sistemde içeren herhangi bir türü dışlar:

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

     `el` "hello" ile eşleşir

-   Ekleme `!` filtre sonuna kadar kesin büyük küçük harfe duyarlı bir eşleşme kolaylaştırır:

     `el!` "hello" eşleşmiyor.

     `hello!` "hello" ile eşleşir

-   Ekleme `*` önek dizesi eşleşen filtre sonuna sağlar:

     `el*` "hello" eşleşmiyor.

     `he*` "hello" ile eşleşir

-   Noktalı virgülle ayrılmış bir listede birden çok filtre bir ayrım birleştirilir:

     `el;wo` "hello" ve "world" ile eşleşir

### <a name="stub-concrete-classes-and-virtual-methods"></a>Saplama somut sınıflar ve sanal yöntemler

Varsayılan olarak, tüm korumalı olmayan sınıfları saplama türlerini üretilir. Soyut sınıflar üzerinden saplama türlerini sınırlamak mümkündür *.fakes* yapılandırma dosyası:

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

### <a name="internal-types"></a>İç türleri

Fakes Kod Oluşturucu dolgusu türleri ve oluşturulan Fakes derleme görünür türleri için saplama türlerini oluşturur. İç türleri shimmed derlemenin Fakes ve test derlemenizi görünür hale getirmek için ekleme <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> öznitelikleri için oluşturulan Fakes derleme ve test derlemesinin görünürlük sağlar shimmed bütünleştirilmiş kodu. Örnek buradadır:

```csharp
// FileSystem\AssemblyInfo.cs
[assembly: InternalsVisibleTo("FileSystem.Fakes")]
[assembly: InternalsVisibleTo("FileSystem.Tests")]
```

 **Türü kesin adlandırılmış derlemelerde iç türleri**

 Shimmed derleme güçlü olarak adlandırılmamış ve bütünleştirilmiş kodun iç türleri erişmek istediğiniz varsa:

-   Test derlemenizi ve Fakes derleme kesin adlandırılmış olmalıdır.

-   Ortak anahtarlar test ve Fakes derlemeye eklemek **Internalsvisibletoattribute** shimmed derlemelerde öznitelikleri. Shimmed derleme güçlü olarak adlandırılmamış zaman shimmed bütünleştirilmiş kodu örnek özniteliklerin nasıl görüneceği aşağıda verilmiştir:

    ```csharp
    // FileSystem\AssemblyInfo.cs
    [assembly: InternalsVisibleTo("FileSystem.Fakes",
        PublicKey=<Fakes_assembly_public_key>)]
    [assembly: InternalsVisibleTo("FileSystem.Tests",
        PublicKey=<Test_assembly_public_key>)]
    ```

Shimmed derleme güçlü olarak adlandırılmamış, Fakes framework kesinlikle otomatik olarak oluşturulan Fakes derleme imzalar. Strong test derlemeyi imzalamak gerekir. Bkz: [tanımlayıcı adlı derlemeler](/dotnet/framework/app-domains/strong-named-assemblies).

Oluşturulan tüm derlemeleri eklemek için bir başlangıç noktası olarak bu parçacığı kullanabilmeniz için imzalamak için aynı anahtar Fakes framework kullanan **InternalsVisibleTo** shimmed derleme kodunuzu fakes derlemeye özniteliği.

```csharp
[assembly: InternalsVisibleTo("FileSystem.Fakes, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e92decb949446f688ab9f6973436c535bf50acd1fd580495aae3f875aa4e4f663ca77908c63b7f0996977cb98fcfdb35e05aa2c842002703cad835473caac5ef14107e3a7fae01120a96558785f48319f66daabc862872b2c53f5ac11fa335c0165e202b4c011334c7bc8f4c4e570cf255190f4e3e2cbc9137ca57cb687947bc")]
```

Fakes derleme için farklı bir ortak anahtar belirtebilirsiniz, bir anahtar gibi tam yolunu belirterek shimmed derleme için oluşturdunuz *.snk* olarak alternatif anahtarı içeren dosya `KeyFile` öznitelik değeri `Fakes` \\ `Compilation` öğesinin *.fakes* dosya. Örneğin:

```xml
<-- FileSystem.Fakes.fakes -->
<Fakes ...>
  <Compilation KeyFile="full_path_to_the_alternate_snk_file" />
</Fakes>
```

Daha sonra diğer ortak anahtarını kullanmak zorunda *.snk* InternalVisibleTo özniteliğinin ikinci parametre olarak bir dosya shimmed bütünleştirilmiş kodu Fakes derlemede için:

```csharp
// FileSystem\AssemblyInfo.cs
[assembly: InternalsVisibleTo("FileSystem.Fakes",
    PublicKey=<Alternate_public_key>)]
[assembly: InternalsVisibleTo("FileSystem.Tests",
    PublicKey=<Test_assembly_public_key>)]
```

Yukarıdaki değerleri örnekte `Alternate_public_key` ve `Test_assembly_public_key` aynı olabilir.

### <a name="optimize-build-times"></a>Yapı kez en iyi duruma getirme

Derleme Fakes derlemelerin, derleme zamanı önemli ölçüde artırabilir. Üçüncü taraf derlemeler ve Fakes derlemeleri .NET sistem derlemeler için ayrı bir merkezi projesi oluşturarak yapı süresini en aza indirebilirsiniz. Bu tür derlemeler nadiren makinenizde değiştiğinden, diğer projeler oluşturulan Fakes derlemelerde yeniden kullanabilirsiniz.

Birim testi projelerini proje klasöründeki FakesAssemblies altına yerleştirilmiş derlenmiş Fakes derlemeler için bir başvuru ekleyin.

1.  .NET çalışma zamanı sürümü test projelerinizi eşleşen yeni bir sınıf kitaplığı oluşturun. Şimdi Fakes.Prebuild çağırın. Kaldırma *class1.cs* gerekli proje dosyasından.

2.  Tüm sistem ve üçüncü taraf derlemeleri Fakes için gereken başvuru ekleyin.

3.  Ekleme bir *.fakes* her derlemeler için dosya ve oluşturun.

4.  Test projenizden

    -   DLL Fakes çalışma zamanı için bir başvuru olduğundan emin olun:

         *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PublicAssemblies\Microsoft.QualityTools.Testing.Fakes.dll*

    -   Oluşturduğunuz her derleme için Fakes için ilgili DLL dosyasında bir başvuru ekleyin *Fakes.Prebuild\FakesAssemblies* projenizin klasör.

### <a name="avoid-assembly-name-clashing"></a>Derleme adı çakışan kaçının

Bir ekip ortamında, tüm yapı çıkışları tek bir dizin birleştirilir. Birden çok proje Fakes kullanırsanız, farklı sürümlerini Fakes derlemelerden birbirlerini geçersiz olabilir. Örneğin, TestProject1 fakes *mscorlib.dll* .NET Framework 2.0 ve TestProject2 fakes gelen *mscorlib.dll* için .NET Framework 4 her ikisi için verecek bir *mscorlib. Fakes.dll* Fakes derleme.

 Bu sorunu önlemek için Fakes otomatik olarak tam sürüm Fakes derleme adları olmayan proje başvuruları için eklerken oluşturmalısınız *.fakes* dosyaları. Fakes derleme adı oluşturduğunuzda sürümü tam Fakes derleme adının bir sürüm numarası katıştırır:

 MyAssembly derleme ve sürüm 1.2.3.4 Fakes derleme MyAssembly.1.2.3.4.Fakes addır.

 Değiştirebilir veya derleme öğesinde sürüm özniteliğini düzenleyerek bu sürümü kaldırmanız *.fakes*:

```xml
attribute of the Assembly element in the .fakes:
<Fakes ...>
  <Assembly Name="MyAssembly" Version="1.2.3.4" />
  ...
</Fakes>
```

## <a name="fakes-naming-conventions"></a>Adlandırma kuralları fakes

### <a name="shim-type-and-stub-type-naming-conventions"></a>Adlandırma kuralları Dolgu türü ve saplama yazın

 **Ad Alanları**

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

### <a name="shim-delegate-property-or-stub-delegate-field-naming-conventions"></a>Adlandırma kuralları dolgusu temsilci özelliği veya saplama temsilci alan

**Temel kurallar** adlandırma, boş bir ad başlatma alan için:

-   Yöntem adı eklenir.

-   Yöntem adı bir açık arabirim uygulaması ise, nokta kaldırılır.

-   Yöntem genel, ise `Of` *n* burada eklenir *n* genel yöntem bağımsız değişkenlerin sayısı.

 **Özel yöntem adları** özelliği gibi alıcı veya ayarlayıcılar aşağıdaki tabloda açıklandığı gibi değerlendirilir:

|Yöntemi ise...|Örnek|Eklenen yöntem adı|
|-------------------|-------------|--------------------------|
|A **Oluşturucusu**|`.ctor`|`Constructor`|
|Statik **Oluşturucusu**|`.cctor`|`StaticConstructor`|
|Bir **erişimci** (örneğin, özellik alıcıları) "_" yöntemi ile ayrılmış iki bölümden oluşan ad|*kind_name* (ortak servis talebi ancak ECMA tarafından zorlanan)|*NameKind*, burada her iki bölümü büyük harfli takas ve|
||Özellik alıcısı `Prop`|`PropGet`|
||Özellik ayarlayıcı `Prop`|`PropSet`|
||Olay ekleyici|`Add`|
||Olay kaldırıcısını|`Remove`|
|Bir **işleci** iki bölümden oluşur|`op_name`|`NameOp`|
|Örneğin: + işleci|`op_Add`|`AddOp`|
|İçin bir **dönüştürme işleci**, dönüş türü eklenir.|`T op_Implicit`|`ImplicitOpT`|

> [!NOTE]
> - **Alıcılar ve ayarlayıcılar dizin oluşturucular,** özelliğine benzer şekilde işlenir. Bir dizin oluşturucu için varsayılan ad `Item`.
> - **Parametre türü** adları dönüştürülen ve birleştirilmiş.
> - **Dönüş türü** aşırı belirsizlik olmadıkça göz ardı edilir. Aşırı amiguity ise, dönüş türü adının sonuna eklenir.

### <a name="parameter-type-naming-conventions"></a>Parametre türü adlandırma kuralları

|Verilen|Eklenen dizedir...|
|-----------|-------------------------|
|A **türü**`T`|T<br /><br /> Ad alanı, iç içe geçmiş yapısı ve genel ı eşleştir bırakılır.|
|Bir **çıkış parametresi**`out T`|`TOut`|
|A **ref parametresi** `ref T`|`TRef`|
|Bir **dizi türü**`T[]`|`TArray`|
|A **çok boyutlu bir dizi** türü `T[ , , ]`|`T3`|
|A **işaretçi** türü `T*`|`TPtr`|
|A **genel tür**`T<R1, ...>`|`TOfR1`|
|A **genel tür bağımsız değişkeni** `!i` türü `C<TType>`|`Ti`|
|A **genel yöntem bağımsız değişkeni** `!!i` yöntemi `M<MMethod>`|`Mi`|
|A **iç içe türü**`N.T`|`N` , ardından eklenir `T`|

### <a name="recursive-rules"></a>Özyinelemeli kuralları

Aşağıdaki kurallar uygulanan yinelemeli olarak şunlardır:

-   Fakes kullandığı için C# Fakes derlemeleri oluşturma için geçersiz bir C# belirteci oluşturur herhangi bir karakter kaçışlı "_" (alt çizgi).

-   Sonuçta elde edilen bir ad bildiri türü herhangi bir üyenin ile çakışıyor numaralandırma düzeni 01 ile başlayan iki basamaklı sayaç ekleyerek kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft Fakes ile test edilen kodu yalıtma](../test/isolating-code-under-test-with-microsoft-fakes.md)
