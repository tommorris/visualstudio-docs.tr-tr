---
title: "Hata ayıklayıcıda yerel nesnelerin özel görünümlerini oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 06/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: natvis
dev_langs: C++
ms.assetid: 2d9a177a-e14b-404f-a6af-49498eff0bd7
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2aa3a6f515ca039c86d453f5729800fe8e1637c0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="create-custom-views-of-native-objects-in-the-visual-studio-debugger"></a>Visual Studio Hata Ayıklayıcısı'ndaki yerel nesnelerin özel görünümlerini oluşturma
Visual Studio Natvis framework Visual Studio hata ayıklayıcı değişken pencerelerini yerel türler görüntüler özelleştirmenize olanak tanır (örneğin, **izleme** penceresinde **Yereller** penceresinde ve  **DataTips**.
  
 Natvis yerini **autoexp.dat** Visual Studio ve teklifleri XML sözdizimi, daha iyi tanılama, sürüm ve birden çok dosya desteği önceki sürümlerinde kullanılan dosya.  
  
> [!NOTE]
>  Görsel Natvis framework kullanamazsınız zaman:  
>   
>  -  Hata ayıklayıcı türü ayarlanan C++ Windows Masaüstü projesinde hata ayıklama **karma**.  
> -   Yönetilen uyumluluk modunda bir Windows masaüstü uygulamasında karışık modda hata ayıklama yapmakta olduğunuz (**Araçlar > Seçenekler > hata ayıklama > Genel > kullanım yönetilen uyumluluk modunda**).  
> -   Yerel uyumluluk modunda bir Windows masaüstü uygulamasında hata ayıklama (**Araçlar > Seçenekler > hata ayıklama > Genel > yerel uyumluluk modu kullan**).  
  
##  <a name="BKMK_Why_create_visualizations_"></a>Neden Natvis görselleştirmeleri oluşturulsun mu?  
 Natvis framework türleri için geliştiricilere bunları kolayca hata ayıklama sırasında görebilmek için oluşturduğunuz görselleştirme kuralları oluşturmak için kullanabilirsiniz.  
  
 Örneğin, aşağıdaki çizimde türünde bir değişken gösterir [Windows::UI::Xaml::Controls::TextBox](http://go.microsoft.com/fwlink/?LinkId=258422) görüntülenen hata ayıklayıcısı'ndaki uygulanan özel görsel.  
  
 ![TextBox varsayılan görselleştirme](../debugger/media/dbg_natvis_textbox_default.png "DBG_NATVIS_TextBox_Default")  
  
 Vurgulanan satır gösterir `Text` özelliği `TextBox` sınıfı. Karmaşık sınıf hiyerarşisi, bu değeri bulmak zorlaştırır; Ayrıca, hata ayıklayıcı textbox içinde tutulan dize göremeyeceği nesne tarafından kullanılan özel bir dize türü yorumlama bilmiyor.  
  
 Aynı `TextBox` özel görselleştirme kuralları uygulandığında değişken penceresinde çok daha kolaydır arar. Sınıf önemli üyeleri birlikte görüntülenebilir ve hata ayıklayıcısı özel bir dize türü temel dize değeri gösterir.  
  
 ![Görselleştirici kullanarak metin kutusuna veri](../debugger/media/dbg_natvis_textbox_visualizer.png "DBG_NATVIS_TextBox_Visualizer")  
  
##  <a name="BKMK_Using_Natvis_files"></a>Natvis dosyalarını kullanma  
 .natvis, XML dosyalarını .natvis uzantısına sahip dosyalardır. Şema tanımlanan **%VSINSTALLDIR%\Xml\Schemas\natvis.xsd**.  
  
 Bir veya daha fazla .natvis dosyasının temel yapısını `Type` öğeleri, burada her `Type` öğesinin temsil ettiği bir görsel öğe girişi tam adı belirtilen bir tür için `Name` özniteliği.  
  
```xml
<?xml version="1.0" encoding="utf-8"?>  
<AutoVisualizer xmlns="http://schemas.microsoft.com/vstudio/debugger/natvis/2010">  
  <Type Name="MyNamespace::CFoo">  
    .  
    .  
  </Type>  
  
  <Type Name="...">  
    .  
    .  
  </Type>  
</AutoVisualizer>  
```  
  
 Visual Studio sağlar bazı .natvis dosyalarında **%VSINSTALLDIR%\Common7\Packages\Debugger\Visualizers** klasör. Bu dosyalar birçok ortak türleri için görselleştirme kuralları içerir ve görselleştirmeleri yeni türleri için yazarken örnek olarak hizmet verebilir.  
  
## <a name="adding-natvis-files-to-your-projects"></a>Projelerinize .natvis dosyaları ekleme  
 Herhangi bir C++ projesine .natvis dosyaları ekleyebilirsiniz.  
  
 Açık bir C++ projesi sahip yeni bir .natvis dosya eklemek için proje düğümünde seçin **Çözüm Gezgini**, tıklatıp **Ekle > Yeni Öğe > Visual C++ > yardımcı programı > hata ayıklayıcı görselleştirme dosya (.natvis)**. Hata ayıklayıcı Natvis dosyaları C++ projeleri otomatik olarak yükler. Varsayılan olarak, projenizin Natvis dosyalarında projenin oluşturduğu .pdb dosyasını da eklenir. Bu, bu projenin oluşturduğu ikili hata ayıklama, açık proje yoksa bile hata ayıklayıcı Natvis dosya .pdb yükleneceğini anlamına gelir. .pdb dahil edilecek .natvis dosya istemiyorsanız .natvis dosyayı sağ tıklatın **Çözüm Gezgini**hem de **yapılandırma özellikleri** penceresi kümesi **yapıdan hariç**  için **Evet**.  
  
 Visual Studio yapılan değişiklikler dosyayı kaydettiğinizde etkili otomatik olarak hata ayıklama sırasında yaptığınız kullanarak Natvis dosyaları düzenleyin önerilir. Ayrıca geliştirilmiş bir düzenleme deneyimi IntelliSense elde edersiniz.  
  
 .Pdb yüklenen Natvis dosyalarına yalnızca pdb başvurduğu modülü türlerinde geçerlidir. Örneğin, Module1.pdb adlı tür için bir giriş tanımlıyorsa `Test`, yalnızca uygulanan bu girişi **Test** Module1.dll sınıfta. Başka bir modül adlı bir sınıf tanımlıyorsa **Test**, Module1.pdb'ın natvis girişi için uygulanmaz.  
  
##  <a name="BKMK_natvis_location"></a>.Natvis dosyaları dağıtma  
 .Natvis dosyanızı yalnızca bir Visual Studio projesi oluşturma türleri için geçerliyse, bir şey yapmanız gerekmez; .natvis .pdb dahil edilir. Birden çok projeye uygulamak istiyorsanız, ancak .natvis dosyaları kullanıcı dizininize veya sistem dizini ekleyebilirsiniz.  
  
 Hangi .natvis dosyaları değerlendirilme sırasını aşağıdaki gibidir:  
  
1.  .natvis dosyaları (yüklenen bir proje ile aynı ada sahip bir dosya zaten sürece) ayıkladığınız .pdb katıştırılmış.  
  
2.  yüklenen C++ projesi veya bir üst düzey çözüm öğesinin parçası olan .natvis dosyaları. Bu grup sınıf kitaplıkları da dahil olmak üzere tüm yüklenen C++ projeleri içerir ancak diğer diller projelerin içermez (örneğin, bir .natvis dosyası bir C# projesinde yüklenemiyor). Yürütülebilir projeleri için kullanılabilir C++ proje olduğundan, zaten bir .pdb içinde mevcut olmayan .natvis dosyalarını barındırmak için çözüm öğeleri kullanmanız gerekir.  
  
3.  Kullanıcıya özgü natvis dizin (örneğin, **%USERPROFILE%\Documents\Visual Studio 2017\Visualizers** veya **%USERPROFILE%\My Documents\Visual Studio 2015\Visualizers**).  
  
4.  Sistem genelinde Natvis dizin (**%VSINSTALLDIR%\Common7\Packages\Debugger\Visualizers**). Bu dizin, Visual Studio ile yüklenen .natvis dosyalarının nerede kopyalanır ' dir. Yönetici izinlerine sahipseniz, bu dizin için diğer dosyaları ekleyebilirsiniz.  
  
## <a name="modifying-natvis-files-while-debugging"></a>Hata ayıklama sırasında .natvis dosyalarını değiştirme  
 IDE .natvis dosyasında dahil edildiği projede hata ayıklarken değiştirebilirsiniz. (İle hata ayıklama Visual Studio'nun aynı örneği kullanarak) IDE'de dosyasını açın, değiştirin ve dosyayı kaydedin. Dosya kaydedilmiş hemen **izleme** ve **Yereller** windows değişikliği yansıtacak şekilde güncelleştirilmesi gerekir. IDE dışında .natvis dosyasını değiştirirseniz, değişiklikler otomatik olarak etkili olmaz. Windows update için değerlendirebilmeniz **.natvisreload** komutunu **izleme** penceresi. Bu eylem, hata ayıklama oturumu başlatmadan etkili olması değişikliklere neden olur.  
  
 Ayrıca, ekleyebilir veya hata ayıklama yaptığınız ve Visual Studio ekler veya kaldırır ilgili görselleştirmeleri bir çözüme .natvis dosyaları silin.  
  
 .Natvis dosya bir .pdb eklendiyse bu hata ayıklarken değiştiremezsiniz.  
  
 Kullanım **.natvisreload** natvis dosya daha yeni bir sürüme (örneğin, kaynak denetimine iade ve bu kişiye başka dosyada yapılan en son değişiklikleri almak istediğiniz varsa) yükseltirken komutu. Visual Studio xml Düzenleyicisi'ni kullanarak natvis dosyaları düzenleyin önerilir.  
  
##  <a name="BKMK_Expressions_and_formatting"></a>İfadeler ve biçimlendirme  
 Natvis görselleştirmeleri C++ ifadeleri görüntülenecek veri öğelerini belirtmek için kullanın. İyileştirmeleri ve C++ ifadeleri açıklanan hata ayıklayıcısında sınırlamaları ek olarak [bağlamı işleci (C++)](../debugger/context-operator-cpp.md), aşağıdaki farklılıklara bilincinde olmanız gerekir:  
  
-   Natvis ifadeler görselleştirilen nesne değil geçerli yığın çerçevesi bağlamında değerlendirilir. Kullanırsanız, örneğin, `x` Natvis ifadesinde tanımlayıcı adlı alanına başvuruyor. `x` , adlı olmayan yerel bir değişkene görselleştirilen nesnedeki `x` şu anda yürütülen işlevinde. Genel değişkenler erişebilirsiniz ancak yerel değişkenler Natvis ifadelerde erişemiyor.  
  
-   İşlev değerlendirmesi veya yan etkileri Natvis ifadeleri izin vermez. Bu işlev çağrılarını ve atama işleçleri göz ardı anlamına gelir. Çünkü [hata ayıklayıcı, iç işlevler](../debugger/expressions-in-the-debugger.md#BKMK_Using_debugger_intrinisic_functions_to_maintain_state) ücretsiz, bunlar serbestçe çağrılabilir herhangi Natvis ifadesinden diğer işlev çağrılarına izin verilmiyor olsa bile yan etkisi olan.  
  
 Bir ifade bir değişken penceresinde nasıl görüntüleneceğini denetlemek için açıklanan biçim belirticileri birini kullanabilirsiniz [biçim belirticileri](../debugger/format-specifiers-in-cpp.md#BKMK_Visual_Studio_2012_format_specifiers) bölümünü [C++ içindeki Biçim belirticileri](../debugger/format-specifiers-in-cpp.md) konu. Sanallaştırma giriş dahili olarak Natvis tarafından gibi kullanıldığında biçim belirticileri göz ardı edilir Not `Size` ifadesinde bir [ArrayItems genişletme](../debugger/create-custom-views-of-native-objects.md#BKMK_ArrayItems_expansion).  
  
## <a name="natvis-views"></a>Natvis görünümleri  
 Natvis görünümler, herhangi bir türü birden fazla şekilde görmek izin verir. Örneğin, adlandırılmış bir görünüm tanımlayabilirsiniz **basit** , bir tür basitleştirilmiş bir görünümünü sağlar. Örneğin, görsel olarak işte `std::vector`:
  
```xml
<Type Name="std::vector&lt;*&gt;">  
    <DisplayString>{{ size={_Mylast - _Myfirst} }}</DisplayString>  
    <Expand>  
        <Item Name="[size]" ExcludeView="simple">_Mylast - _Myfirst</Item>  
        <Item Name="[capacity]" ExcludeView="simple">_Myend - _Myfirst</Item>  
        <ArrayItems>  
            <Size>_Mylast - _Myfirst</Size>  
            <ValuePointer>_Myfirst</ValuePointer>  
        </ArrayItems>  
    </Expand>  
</Type>  
```  
  
 `DisplayString` Ve `ArrayItems` öğeleri varsayılan görünüm ve basit bir görünümle kullanılır sırada `[size]` ve `[capacity]` öğeleri basit görünümünden dışlanır. Kullanabileceğiniz **, Görünüm** alternatif görünümü belirtmek için belirleyici biçimlendirin. İçinde **izleme** penceresinde, belirttiğiniz basit görünüm olarak **vec,view(simple)**:  
  
 ![Gözcü penceresi basit görünümüyle](../debugger/media/watch-simpleview.png "izleme SimpleView")  
  
##  <a name="BKMK_Diagnosing_Natvis_errors"></a>Natvis hatalarını tanılama  
 Sözdizimi sorun giderme ve hata ayrıştırmak için Natvis Tanılama'yı kullanabilirsiniz. Hata ayıklayıcı bir görsel öğe girişi hatalarla karşılaştığında, hataları ve her iki görüntüler ham biçimde türü yoksayar veya başka bir uygun görselleştirme seçer. Belirli bir görsel öğe girişi neden yoksayılır anlamak ve temel alınan hataları nelerdir görmek için Natvis Tanılama'yı açmak **Araçlar > Seçenekler > hata ayıklama > Çıktı penceresi > Natvis tanılama iletileri (C++ yalnızca)** seçeneği. Hataları görüntülenen **çıkış** penceresi.  
  
##  <a name="BKMK_Syntax_reference"></a>Natvis söz dizimi başvurusu  
  
###  <a name="BKMK_AutoVisualizer"></a>AutoVisualizer öğesi  
 `AutoVisualizer` Öğesi .natvis dosyasının kök düğüm ve ad alanını içeren `xmlns:` özniteliği.  
  
```xml
<?xml version="1.0" encoding="utf-8"?>  
<AutoVisualizer xmlns="http://schemas.microsoft.com/vstudio/debugger/natvis/2010">  
.  
.  
</AutoVisualizer>  
```  
  
###  <a name="BKMK_Type"></a>Type öğesi  
 Temel türü şöyle görünür:  
  
```xml
<Type Name="[fully qualified type name]">  
  <DisplayString Condition="[Boolean expression]">[Display value]</DisplayString>  
  <Expand>  
    ...  
  </Expand>  
</Type>  
```  
  
 Belirtir:  
  
1.  Ne tür bir bu görselleştirme için kullanılması gereken ( `Type Name` özniteliği).  
  
2.  Bu türdeki bir nesnenin değerini aşağıdaki gibi görünmelidir ( `DisplayString` öğesi).  
  
3.  Tür üyeleri zaman kullanıcı, bir değişken penceresinde genişletir gibi görünmelidir ( `Expand` düğüm).  
  
 **Şablonlu sınıfları** `Name` özniteliği `Type` öğesi kabul eden bir yıldız işareti `*` şablonlu sınıf adları için kullanılan bir joker karakter olarak:  
  
```xml
<Type Name="ATL::CAtlArray&lt;*&gt;">  
    <DisplayString>{{Count = {m_nSize}}}</DisplayString>  
</Type>  
  
```  
  
 Bu örnekte, aynı görselleştirme kullanılır, bu nesne olup bir `CAtlArray<int>` veya `CAtlArray<float>`. Bir özel görsel öğe girişi için ise bir `CAtlArray<float>`, sonra da genel bir öncelik kazanır.  
  
 Şablon parametreleri görsel öğe girişi makroları $T1, $T2, kullanarak başvurulabilir ve benzeri unutmayın. Bu makroları örneklerini bulmak için Visual Studio ile birlikte gelen .natvis dosyalarına bakın.  
  
####  <a name="BKMK_Visualizer_type_matching"></a>Görselleştirici türüyle eşleşen  
 Doğrulamak bir görsel öğe girişi başarısız olursa, sonraki kullanılabilir görselleştirme kullanılır.  
  
#### <a name="inheritable-attribute"></a>Devralınabilir özniteliği  
 Bir görsel öğe yalnızca bir temel türe veya bir taban türü ve isteğe bağlı olan tüm türetilmiş türler için geçerli olup olmadığını belirtebilirsiniz `Inheritable` özniteliği. Aşağıda, görselleştirme için yalnızca geçerli `BaseClass` türü:  
  
```xml
<Type Name="Namespace::BaseClass" Inheritable="true">  
    <DisplayString>{{Count = {m_nSize}}}</DisplayString>  
</Type>  
```  
  
 Varsayılan değer olan `Inheritable` olan `true`.  
  
#### <a name="priority-attribute"></a>Öncelik özniteliği  
 `Priority` Özniteliği, alternatif tanımları ayrıştırmak bir tanım başarısız olursa sırayla kullanılacağını belirtir. Olası değerlerini `Priority` şunlardır: `Low`, `MediumLow`,`Medium`, `MediumHigh`, ve `High`, ve varsayılan değer `Medium`.  
  
 Öncelik özniteliği yalnızca öncelikleri farklı dosyalar arasında değil aynı .natvis dosya içinde ayırt etmek için kullanılmalıdır.  
  
 Aşağıdaki örnekte, biz öncelikle 2015 STL eşleşen giriş ayrıştırabilir ve ayrıştırmak başarısız olursa, diğer giriş STL 2013 sürümü için kullanırız:  
  
```xml
<!-- VC 2013 -->  
<Type Name="std::reference_wrapper&lt;*&gt;" Priority="MediumLow">  
     <DisplayString>{_Callee}</DisplayString>  
    <Expand>  
        <ExpandedItem>_Callee</ExpandedItem>  
    </Expand>  
</Type>  
  
<!-- VC 2015 -->  
<Type Name="std::reference_wrapper&lt;*&gt;">  
    <DisplayString>{*_Ptr}</DisplayString>  
    <Expand>  
        <Item Name="[ptr]">_Ptr</Item>  
    </Expand>  
</Type>  
```  
  
####  <a name="BKMK_Versioning"></a>Sürüm öğesi  
 Kullanım `Version` kapsam görselleştirmeleri belirli modüller ve çakışma ad şekilde sürümlerine öğesine ve simge durumuna farklı görselleştirme türlerinin farklı sürümleri için kullanılabilir. Örneğin:  
  
```xml
<Type Name="DirectUI::Border">  
  <Version Name="Windows.UI.Xaml.dll" Min="1.0" Max="1.5"/>  
  <DisplayString>{{Name = {*(m_pDO->m_pstrName)}}}</DisplayString>  
  <Expand>  
    <ExpandedItem>*(CBorder*)(m_pDO)</ExpandedItem>  
  </Expand>  
</Type>  
```  
  
 Bu örnekte görselleştirme için yalnızca geçerli `DirectUI::Border` bulunan türü `Windows.UI.Xaml.dll` 1.5 1.0 sürümünden. Sürüm öğe eklemek belirli modülü ve sürüm görselleştirme girişe kapsamları ve yanlışlıkla uyuşmazlıkları azaltır. Ancak, bir türü farklı modülleri tarafından kullanılan ortak bir üstbilgi dosyasında tanımlanmış olması durumunda, türü Belirtilen modül olmadığında sürümlü görselleştirme uygulanmıyor.  
  
#### <a name="optional-attribute"></a>İsteğe bağlı özniteliği  
 `Optional` Özniteliği, herhangi bir düğümde görünebilir. Ayrıştırmak isteğe bağlı bir düğüm içindeki tüm alt başarısız olursa, o düğümde göz ardı edilir, ancak türü öğesi kalan hala geçerlidir. Aşağıdaki türde `[State]` olmayan-isteğe bağlıdır, ancak `[Exception]` isteğe bağlıdır.  Bu olması durumunda anlamına gelir `MyNamespace::MyClass` _ adlı bir alan içeriyor`M_exceptionHolder`, her ikisi de görmeye devam `[State]` düğümü ve `[Exception]` varsa ancak düğüm `_M_exceptionHolder` , yalnızca gördüğünüz eksik `[State]` düğümü.
  
```xml
<Type Name="MyNamespace::MyClass">  
    <Expand>  
      <Item Name="[State]">_M_State</Item>  
      <Item Name="[Exception]" Optional="true">_M_exceptionHolder</Item>  
    </Expand>  
</Type>  
```  
  
###  <a name="BKMK_Condition_attribute"></a>Koşul özniteliği  
 İsteğe bağlı `Condition` öznitelik birçok görselleştirme öğeler için kullanılabilir ve görselleştirme kuralı ne zaman kullanılacağını belirtir. Koşul özniteliğinde ifade için çözümlenirse `false`, sonra da öğesi tarafından belirtilen görselleştirme kural uygulanmaz. Doğru olarak değerlendirilirse veya varsa hiçbir `Condition` özniteliği sonra görselleştirme kural türü için uygulanır. Bu öznitelik için kullanabileceğiniz `if-else` görselleştirme girişleri mantığı. Örneğin, aşağıdaki görselleştirme iki sahip `DisplayString` akıllı işaretçi türü için öğeleri:  
  
```xml
<Type Name="std::auto_ptr&lt;*&gt;">  
  <DisplayString Condition="_Myptr == 0">empty</DisplayString>  
  <DisplayString>auto_ptr {*_Myptr}</DisplayString>  
  <Expand>  
    <ExpandedItem>_Myptr</ExpandedItem>  
  </Expand>  
</Type>  
  
```  
  
 Zaman `_Myptr` üye `null`, ilk koşul `DisplayString` öğesi çözümler için `true`, böylece form görüntülenir. Zaman `_Myptr` üyesi olmayan `null`, için koşulu değerlendirir `false`ve ikinci `DisplayString` öğesi görüntülenir.  
  
### <a name="includeview-and-excludeview-attributes"></a>IncludeView ve ExcludeView öznitelikleri  
 Bu öznitelikler, görüntülenen veya farklı görünümlerde görüntülenmeyen öğelerini belirtin. Örneğin, Natvis belirtimini verilen `std::vector`:  
  
```xml
<Type Name="std::vector&lt;*&gt;">  
    <DisplayString>{{ size={_Mylast - _Myfirst} }}</DisplayString>  
    <Expand>  
        <Item Name="[size]" ExcludeView="simple">_Mylast - _Myfirst</Item>  
        <Item Name="[capacity]" ExcludeView="simple">_Myend - _Myfirst</Item>  
        <ArrayItems>  
            <Size>_Mylast - _Myfirst</Size>  
            <ValuePointer>_Myfirst</ValuePointer>  
        </ArrayItems>  
    </Expand>  
</Type>  
```  
  
 Basit bir görünümle [boyutu] göstermez ve basit bir görünümle [kapasite] öğeler. Kullansaydık `IncludeView="simple"` yerine `ExcludeView`, `[size]` ve `[capacity]` öğeleri getirirseniz, basit bir görünümle yerine varsayılan görünüm.  
  
 Kullanabileceğiniz `IncludeView` ve `ExcludeView` öznitelikleri tek tek üyeleri yanı sıra türleri.  
  
###  <a name="BKMK_DisplayString"></a>DisplayString  
 A `DisplayString` öğesi değişkenin değeri görüntülenecek dizeyi belirtir. Bu ifadelerle karma rastgele dizeleri kabul eder. Süslü ayraçlar içindeki tüm öğeler bir ifade olarak yorumlanır. Örneğin, bir `DisplayString` aşağıdaki gibi girişi:  
  
```xml
<Type Name="CPoint">  
  <DisplayString>{{x={x} y={y}}}</DisplayString>   
</Type>  
  
```  
  
 Yol türü bu değişkenleri `CPoint` Bu örnekte olduğu gibi görüntülenir:  
  
 ![DisplayString öğesi kullanılarak](../debugger/media/dbg_natvis_cpoint_displaystring.png "DBG_NATVIS_CPoint_DisplayString")  
  
 İçinde `DisplayString` ifadesi `x` ve `y`, üyeleri olan `CPoint`, süslü ayraçlar içinde olan ve değerlerine değerlendirilir. Çift süslü ayraçlar kullanarak kaşlı ayraç nasıl kaçınmak ifade ayrıca gösterir ( `{{` veya `}}` ).  
  
> [!NOTE]
>  `DisplayString` Öğesidir rastgele dizeleri ve kaşlı ayraç sözdizimi kabul eden yalnızca. Diğer tüm görselleştirme öğeleri hata ayıklayıcı tarafından değerlendirilen ifadeleri kabul edin.  
  
###  <a name="BKMK_StringView"></a>StringView  
 `StringView` Öğesi değeri yerleşik metin Görselleştirici gönderilmek üzere olduğuna ifade tanımlar. Örneğin, aşağıdaki görselliğini sahibiz varsayalım `ATL::CStringT` türü:  
  
```xml
<Type Name="ATL::CStringT&lt;wchar_t,*&gt;">  
  <DisplayString>{m_pszData,su}</DisplayString>  
</Type>
```  
  
 Görselleştirme görüntüler bir `CStringT` nesne bir değişken penceresinde şuna benzer:   
  
 ![CStringT DisplayString öğesi](../debugger/media/dbg_natvis_displaystring_cstringt.png "DBG_NATVIS_DisplayString_CStringT")  
  
 Ekleme bir `StringView` öğesi, bu değer metin görselleştirme tarafından görüntülenebilir için hata ayıklayıcı gösterir:  
  
```xml
<Type Name="ATL::CStringT&lt;wchar_t,*&gt;">
  <DisplayString>{m_pszData,su}</DisplayString>  
  <StringView>m_pszData,su</StringView>  
</Type>  
```  
  
 Değer yanında gösterilen Büyüteç simgesini dikkat edin. Simgesini seçerek dize görüntüleyen metni Görselleştirici başlatır, `m_pszData` işaret eder.  
  
 ![StringView görselleştiricisi CStringT verilerle](../debugger/media/dbg_natvis_stringview_cstringt.png "DBG_NATVIS_StringView_CStringT")  
  
> [!NOTE]
>  Unutmayın ifade `{m_pszData,su}` C++ biçim belirticisi içeren `su` bir UNICODE dizesi değerini görüntülemek için. Bkz: [C++ içindeki Biçim belirticileri](../debugger/format-specifiers-in-cpp.md) daha fazla bilgi için.  
  
###  <a name="BKMK_Expand"></a>Genişletme  
 `Expand` Düğüm isteğe bağlı olarak kullanıcı değişken Windows'da genişletir görselleştirilmiş türündeki alt öğeleri özelleştirmek için kullanılır. Bu, alt öğelerini tanımlama alt düğümleri listesini kabul eder.  
  
 `Expand` Düğümdür isteğe bağlıdır.  
  
-   Varsa bir `Expand` düğümü belirtilmemiş bir görsel öğe girişi Visual Studio'nun varsayılan genişletme kuralları kullanılır.  
  
-   Varsa bir `Expand` düğümü belirtilmesi, altında hiçbir alt düğümler ile türü olmaz Genişletilebilir hata ayıklayıcı pencerelerinde.  
  
####  <a name="BKMK_Item_expansion"></a>Öğesi genişletmesi  
 `Item` Öğesidir en temel hem de kullanılan en yaygın öğesi bir `Expand` düğümü. `Item`tek bir alt öğe tanımlar. Örneğin, sahip olduğunuzu varsayın bir `CRect` ile sınıf `top`, `left`, `right`, ve `bottom` alanları ve aşağıdaki görsel öğe girişi olarak:  
  
```xml
<Type Name="CRect">  
  <DisplayString>{{top={top} bottom={bottom} left={left} right={right}}}</DisplayString>  
  <Expand>  
    <Item Name="Width">right - left</Item>  
    <Item Name="Height">bottom - top</Item>  
  </Expand>  
</Type>  
  
```  
  
 `CRect` Türü şöyle görünür:  
  
 ![Öğesi öğesi genişletmesi ile CRect](../debugger/media/dbg_natvis_expand_item_crect1.png "DBG_NATVIS_Expand_Item_CRect1")  
  
 Belirtilen ifadeleri `Width` ve `Height` öğeleri değerlendirilir ve değerin sütununda gösterilen. `[Raw View]` Özel genişletme kullanıldığı her düğüm hata ayıklayıcı tarafından otomatik olarak oluşturulur. Nesnenin ham görünümünü nasıl kendi görselleştirme farklı olduğunu göstermek için yukarıdaki ekran görüntüsü genişletilir. Visual Studio varsayılan genişletme taban sınıfı için bir alt ağacı oluşturur ve tüm veri üyeleri temel sınıfın alt öğeleri olarak listeler.  
  
> [!NOTE]
>  Öğe unsuru ifade karmaşık bir türe işaret ediyorsa `Item` düğüm genişletilebilir.  
  
####  <a name="BKMK_ArrayItems_expansion"></a>ArrayItems genişletme  
 Kullanım `ArrayItems` türü bir dizi olarak yorumlar ve bireysel öğeleri görüntülemek Visual Studio hata ayıklayıcısı sahip düğümü. Görselliğini `std::vector` iyi bir örnektir:  
  
```xml
<Type Name="std::vector&lt;*&gt;">  
  <DisplayString>{{size = {_Mylast - _Myfirst}}}</DisplayString>  
  <Expand>  
    <Item Name="[size]">_Mylast - _Myfirst</Item>  
    <Item Name="[capacity]">(_Myend - _Myfirst)</Item>  
    <ArrayItems>  
      <Size>_Mylast - _Myfirst</Size>  
      <ValuePointer>_Myfirst</ValuePointer>  
    </ArrayItems>  
  </Expand>  
</Type>  
```  
  
 A `std::vector` değişken penceresinde genişletildiğinde, bireysel öğeleri gösterir:  
  
 ![ArrayItems genişletme ile std::vector](../debugger/media/dbg_natvis_expand_arrayitems_stdvector.png "DBG_NATVIS_Expand_ArrayItems_StdVector")  
  
 En azından, `ArrayItems` düğüm olması gerekir:  
  
1.  A `Size` (bir tamsayı olarak değerlendirmeniz gerekir) ifade dizi uzunluğu anlamak hata ayıklayıcısı  
  
2.  A `ValuePointer` ilk öğeye işaret etmelidir ifade (olmayan bir öğe türü bir işaretçi olmalıdır `void*`).  
  
 Varsayılan değer olan dizi alt sınırı 0'dır. Değer kullanılarak geçersiz kılınabilir bir `LowerBound` öğesi (örnekler bulunabilir Visual Studio ile birlikte gelen .natvis dosyaları).  
  
 Artık kullanabilirsiniz `[]` işleciyle bir `ArrayItems` örneğin genişletme `vector[i]`. [] İşleci kullanan bir tek boyutlu dizi hiçbir görselleştirme kullanılabilir `ArrayItems` veya `IndexListItems`türü bu işleç izin verme olsa bile (örneğin `CATLArray`).  
  
 Çok boyutlu diziler de belirtilebilir. Hata ayıklayıcı düzgün bu durumda alt öğelerini görüntülemek için biraz daha fazla bilgi gerekiyor:  
  
```xml
<Type Name="Concurrency::array&lt;*,*&gt;">  
  <DisplayString>extent = {_M_extent}</DisplayString>  
  <Expand>  
    <Item Name="extent">_M_extent</Item>  
    <ArrayItems Condition="_M_buffer_descriptor._M_data_ptr != 0">  
      <Direction>Forward</Direction>  
      <Rank>$T2</Rank>  
      <Size>_M_extent._M_base[$i]</Size>  
      <ValuePointer>($T1*) _M_buffer_descriptor._M_data_ptr</ValuePointer>  
    </ArrayItems>  
  </Expand>  
</Type>  
```  
  
 `Direction`dizi ana satır veya sütun ana sıralama olup olmadığını belirtir. `Rank`dizi derecesini belirtir. `Size` Öğesi kabul örtük `$i` dizi uzunluğu, bu boyut bulmak için boyut diziniyle değiştirir parametresi. Örneğin, önceki örnekte, ifade yukarıda `_M_extent.M_base[0]` 0 boyutun uzunluğu vermelidir `_M_extent._M_base[1]` 1 ve benzeri.  
  
 İki boyutlu bir nasıl işte `Concurrency::array` nesne Hata Ayıklayıcısı'ndaki görünür:  
  
 ![İki boyutlu dizi ArrayItems genişletmeyle](../debugger/media/dbg_natvis_expand_arrayitems_2d.png "DBG_NATVIS_Expand_ArrayItems_2D")  
  
####  <a name="BKMK_IndexListItems_expansion"></a>IndexListItems genişletme  
 Kullanabileceğiniz `ArrayItems` yalnızca dizi öğeleri bitişik bellek düzenlenmiştir varsa genişletme. Hata ayıklayıcı geçerli öğe için kendi işaretçi artırılarak sonraki öğeye alır. Dizin değeri düğüme işlemek için ihtiyaç duyacağınız durumlarını desteklemek üzere `IndexListItems` düğümleri kullanılabilir. Bir görsel öğe İşte kullanarak `IndexListItems` düğümü:  
  
```xml
<Type Name="Concurrency::multi_link_registry&lt;*&gt;">  
  <DisplayString>{{size = {_M_vector._M_index}}}</DisplayString>  
  <Expand>  
    <Item Name="[size]">_M_vector._M_index</Item>  
    <IndexListItems>  
      <Size>_M_vector._M_index</Size>  
      <ValueNode>*(_M_vector._M_array[$i])</ValueNode>  
    </IndexListItems>  
  </Expand>  
</Type>  
```  
  
 Artık kullanabilirsiniz `[]` işleciyle bir `IndexListItems` örneğin genişletme `vector[i]`. `[]` İşlecini kullanan bir tek boyutlu dizi hiçbir görselleştirme kullanılabilir `ArrayItems` veya `IndexListItems`türü bu işleç izin verme olsa bile (örneğin `CATLArray`).  
  
 Arasındaki tek fark `ArrayItems` ve `IndexListItems` olan `ValueNode` i tam ifade bekliyor<sup>th</sup> örtük öğeyle `$i` parametresi.  
  
####  <a name="BKMK_LinkedListItems_expansion"></a>LinkedListItems genişletme  
 Bağlantılı bir liste görselleştirilmiş türü temsil ediyorsa, hata ayıklayıcı alt öğelerini kullanarak görüntüleyebilirsiniz bir `LinkedListItems` düğümü. Görselliğini işte `CAtlList` bu özelliği kullanarak yazın:  
  
```xml
<Type Name="ATL::CAtlList&lt;*,*&gt;">  
  <DisplayString>{{Count = {m_nElements}}}</DisplayString>  
  <Expand>  
    <Item Name="Count">m_nElements</Item>  
    <LinkedListItems>  
      <Size>m_nElements</Size>  
      <HeadPointer>m_pHead</HeadPointer>  
      <NextPointer>m_pNext</NextPointer>  
      <ValueNode>m_element</ValueNode>  
    </LinkedListItems>  
  </Expand>  
</Type>  
```  
  
 `Size` Öğeyi listenin uzunluğu eder. `HeadPointer`ilk öğesine işaret eden `NextPointer` sonraki öğeye başvuruyor ve `ValueNode` öğenin değerini gösterir.  
  
-   `NextPointer` Ve `ValueNode` ifadeleri bağlantılı liste düğümü öğesi ve üst liste türü bağlamında değerlendirilir. Önceki örnekte `CAtlList` sahip bir `CNode` sınıfı (bulunan `atlcoll.h`), bağlantılı listesinin bir düğümü temsil eder. `m_pNext`ve `m_element` bu alanlar `CNode` sınıfı değil, `CAtlList` sınıfı.  
  
-   `ValueNode` Boş bırakılabilir veya sahip `this` bağlantılı liste düğümüne kendisini başvurmak için.  
  
#### <a name="customlistitems-expansion"></a>CustomListItems genişletme  
 `CustomListItems` Genişletme bir hashtable gibi bir veri yapısı geçiş için özel mantığınızı yazmanızı sağlar. Kullanmanız gereken `CustomListItems` görselleştirmek için hangi her şeyi ihtiyacınız değerlendirmek yapıları C++ ifadeleri ifade olmakla birlikte, kalıbına için oldukça uygun olmayan `ArrayItems`, `TreeItems`, veya`LinkedListItems.`  
  
 Görselleştirici CAtlMap için mükemmel örneğidir burada `CustomListItems` uygundur.  
  
```xml
<Type Name="ATL::CAtlMap&lt;*,*,*,*&gt;">  
    <AlternativeType Name="ATL::CMapToInterface&lt;*,*,*&gt;"/>  
    <AlternativeType Name="ATL::CMapToAutoPtr&lt;*,*,*&gt;"/>  
    <DisplayString>{{Count = {m_nElements}}}</DisplayString>  
    <Expand>  
      <CustomListItems MaxItemsPerView="5000" ExcludeView="Test">  
        <Variable Name="iBucket" InitialValue="-1" />  
        <Variable Name="pBucket" InitialValue="m_ppBins == nullptr ? nullptr : *m_ppBins" />  
        <Variable Name="iBucketIncrement" InitialValue="-1" />  
  
        <Size>m_nElements</Size>  
        <Exec>pBucket = nullptr</Exec>  
        <Loop>  
          <If Condition="pBucket == nullptr">  
            <Exec>iBucket++</Exec>  
            <Exec>iBucketIncrement = __findnonnull(m_ppBins + iBucket, m_nBins - iBucket)</Exec>  
            <Break Condition="iBucketIncrement == -1" />  
            <Exec>iBucket += iBucketIncrement</Exec>  
            <Exec>pBucket = m_ppBins[iBucket]</Exec>  
          </If>  
          <Item>pBucket,na</Item>  
          <Exec>pBucket = pBucket->m_pNext</Exec>  
        </Loop>  
      </CustomListItems>  
    </Expand>  
</Type>  
```  

Kullanabileceğiniz `Exec` içine kod yürütmek için bir `CustomListItems` tanımlanan nesneleri ve değişkenleri kullanarak genişletme `CustomListItems` genişletme. Kullanamazsınız `Exec` işlevleri değerlendirmek için.

Mantıksal işleçler, aritmetik işleçler ve atama işleçleri ile kullanabilmeniz için `Exec`.

Aşağıdaki iç işlevler desteklenir:

- `strlen, wcslen, strnlen, wcsnlen, strcmp, wcscmp, _stricmp, _strcmpi, _wcsicmp, strncmp, wcsncmp, _strnicmp, _wcsnicmp, memcmp, memicmp, wmemcmp, strchr, wcschr, memchr, wmemchr, strstr, wcsstr, __log2, __findNonNull`
- `GetLastError, TlsGetValue, DecodeHString, WindowsGetStringLen, WindowsGetStringRawBuffer, WindowsCompareStringOrdinal, RoInspectCapturedStackBackTrace, CoDecodeProxy, GetEnvBlockLength, DecodeWinRTRestrictedException, DynamicMemberLookup, DecodePointer, DynamicCast`
- `ConcurrencyArray_OperatorBracket_idx // Concurrency::array<>::operator[index<>] and operator(index<>)`
- `ConcurrencyArray_OperatorBracket_int // Concurrency::array<>::operator(int, int, ...)`
- `ConcurrencyArray_OperatorBracket_tidx // Concurrency::array<>::operator[tiled_index<>] and operator(tiled_index<>)`
- `ConcurrencyArrayView_OperatorBracket_idx // Concurrency::array_view<>::operator[index<>] and operator(index<>)`
- `ConcurrencyArrayView_OperatorBracket_int // Concurrency::array_view<>::operator(int, int, ...)`
- `ConcurrencyArrayView_OperatorBracket_tidx // Concurrency::array_view<>::operator[tiled_index<>] and operator(tiled_index<>)`
- `Stdext_HashMap_Int_OperatorBracket_idx`
- `Std_UnorderedMap_Int_OperatorBracket_idx`
- `TreeTraverse_Init // Initializes a new tree traversal`
- `TreeTraverse_Next // Returns nodes in a tree`
- `TreeTraverse_Skip // Skips nodes in a pending tree traversal`
  
####  <a name="BKMK_TreeItems_expansion"></a>TreeItems genişletme  
 Görselleştirilmiş türü bir ağaç temsil ediyorsa, hata ayıklayıcı ağaç yol ve kullanarak, alt öğelerini görüntülemek bir `TreeItems` düğümü. Görselliğini işte `std::map` bu özelliği kullanarak yazın:  
  
```xml
<Type Name="std::map&lt;*&gt;">  
  <DisplayString>{{size = {_Mysize}}}</DisplayString>  
  <Expand>  
    <Item Name="[size]">_Mysize</Item>  
    <Item Name="[comp]">comp</Item>  
    <TreeItems>  
      <Size>_Mysize</Size>  
      <HeadPointer>_Myhead->_Parent</HeadPointer>  
      <LeftPointer>_Left</LeftPointer>  
      <RightPointer>_Right</RightPointer>  
      <ValueNode Condition="!((bool)_Isnil)">_Myval</ValueNode>  
    </TreeItems>  
  </Expand>  
</Type>  
```  
  
 Sözdizimi benzer `LinkedListItems` düğümü. `LeftPointer`, `RightPointer`, ve `ValueNode` ağaç düğümü sınıfı bağlamında değerlendirilir ve `ValueNode` boş bırakılabilir veya sahip `this` ağaç düğümü kendisini başvurmak için.  
  
####  <a name="BKMK_ExpandedItem_expansion"></a>ExpandedItem genişletme  
 `ExpandedItem` Öğesi, görselleştirilmiş türündeki alt öğeleri değilmiş gibi temel sınıfları veya veri üye özelliklerini görüntüleyerek bir toplanmış alt görünüm oluşturmak için kullanılabilir. Belirtilen ifade değerlendirilir ve sonucun alt düğümleri görselleştirilmiş türü alt listesine eklenir. Örneğin, bir akıllı işaretçi türü sahibiz varsayalım `auto_ptr<vector<int>>`, genellikle görüntüleyen olarak:  
  
 ![Otomatik &#95; ptr &#60; vektör &#60; int &#62; &#62; Varsayılan genişletme](../debugger/media/dbg_natvis_expand_expandeditem_default.png "DBG_NATVIS_Expand_ExpandedItem_Default")  
  
 Vektör değerlerini görmek için _Myptr üyesi üzerinden geçirme değişken penceresinde iki düzey detaya gerekir. Ekleyerek bir `ExpandedItem` öğesi, ortadan kaldırabilir `_Myptr` değişkeni hiyerarşiden ve doğrudan vektör öğeleri görüntüleyin::  
  
```xml
<Type Name="std::auto_ptr&lt;*&gt;">  
  <DisplayString>auto_ptr {*_Myptr}</DisplayString>  
  <Expand>  
    <ExpandedItem>_Myptr</ExpandedItem>  
  </Expand>  
</Type>  
```  
  
 ![Otomatik &#95; ptr &#60; vektör &#60; int &#62; &#62; ExpandedItem genişletme](../debugger/media/dbg_natvis_expand_expandeditem_visualized.png "DBG_NATVIS_Expand_ExpandedItem_Visualized")  
  
 Aşağıdaki örnek, temel sınıfından türetilmiş bir sınıf içinde özellikleri toplama gösterilmektedir. Varsayalım `CPanel` sınıfı türer `CFrameworkElement`. Taban gelen özellikleri yinelenen yerine `CFrameworkElement` sınıfı, `ExpandedItem` düğümü, bu özellikler, alt listesine eklenecek sağlar `CPanel` sınıfı. **Nd** türetilmiş sınıf için eşleşen görselleştirme devre dışı bırakır, biçim belirticisi hazır gerekli. Aksi takdirde, ifade `*(CFrameworkElement*)this` neden `CPanel` varsayılan görselleştirme yazın çünkü eşleştirme kurallarına yeniden uygulanması için görselleştirme, en uygun olanı düşünün. Kullanarak **nd** biçim belirticisi temel sınıfı bir görsel öğe yoksa, temel sınıf görselleştirme veya temel sınıf varsayılan genişletme kullanmak için hata ayıklayıcı bildirir.  
  
```xml
<Type Name="CPanel">  
  <DisplayString>{{Name = {*(m_pstrName)}}}</DisplayString>  
  <Expand>  
    <Item Name="IsItemsHost">(bool)m_bItemsHost</Item>  
    <ExpandedItem>*(CFrameworkElement*)this,nd</ExpandedItem>  
  </Expand>  
</Type>  
```  
  
####  <a name="BKMK_Synthetic_Item_expansion"></a>Yapay öğesi genişletmesi  
 Burada `ExpandedItem` öğesi hiyerarşileri ortadan kaldırarak verileri daha düz bir görünümünü sağlar `Synthetic` düğümü karşıtı yapar. Yapay alt öğesi (diğer bir deyişle, bir ifadenin sonucunu olmayan bir alt öğesi) oluşturmanızı sağlar. Bu alt öğesi, kendi alt öğeleri içerebilir. Aşağıdaki örnekte, görselliğini `Concurrency::array` türü kullanan bir `Synthetic` kullanıcı için bir tanılama iletisi göstermek için düğümünü:  
  
```xml
<Type Name="Concurrency::array&lt;*,*&gt;">  
  <DisplayString>extent = {_M_extent}</DisplayString>  
  <Expand>  
    <Item Name="extent" Condition="_M_buffer_descriptor._M_data_ptr == 0">_M_extent</Item>  
    <ArrayItems Condition="_M_buffer_descriptor._M_data_ptr != 0">  
      <Rank>$T2</Rank>  
      <Size>_M_extent._M_base[$i]</Size>  
      <ValuePointer>($T1*) _M_buffer_descriptor._M_data_ptr</ValuePointer>  
    </ArrayItems>  
    <Synthetic Name="Array" Condition="_M_buffer_descriptor._M_data_ptr == 0">  
      <DisplayString>Array members can be viewed only under the GPU debugger</DisplayString>  
    </Synthetic>  
  </Expand>  
</Type>  
  
```  
  
 ![Yapay öğesi genişletmeyle CONCURRENCY::Array](../debugger/media/dbg_natvis_expand_synthetic.png "DBG_NATVIS_Expand_Synthetic")  
  
###  <a name="BKMK_HResult"></a>HResult  
 `HResult` Öğesi HRESULT hata ayıklayıcı Windows için görüntülenen bilgileri özelleştirmenize olanak sağlar. `HRValue` Öğesi özelleştirilmek üzere HRESULT 32-bit değerini içermelidir. `HRDescription` Öğesi ayıklayıcıda görüntülenen bilgileri içerir.  
  
```  
  
<HResult Name="MY_E_COLLECTION_NOELEMENTS">  
  <HRValue>0xABC0123</HRValue>  
  <HRDescription>No elements in the collection.</HRDescription>  
</HResult>  
```  
  
###  <a name="BKMK_UIVisualizer"></a>UIVisualizer  
 A `UIVisualizer` öğesi eklenti grafik Görselleştirici hata ayıklayıcısı ile kaydeder. Eklenti grafik Görselleştirici iletişim kutusu veya bir değişken veya nesne veri türü için uygun bir şekilde görüntülemek için başka bir arabirim oluşturur. Eklenti Görselleştirici olarak yazılmayı bir [VSPackage](../extensibility/internals/vspackages.md) ve hata ayıklayıcı tarafından kullanılabilecek bir hizmeti kullanıma gerekiyor. .Natvis dosya adını, kullanıma sunulan hizmet GUID'i ve ayrıca bu görselleştirebilirsiniz türleri gibi eklenti için kayıt bilgileri içerir.  
  
 Bir UIVisualizer öğesinin bir örneği burada verilmiştir:  
  
```xml
<?xml version="1.0" encoding="utf-8"?>  
<AutoVisualizer xmlns="http://schemas.microsoft.com/vstudio/debugger/natvis/2010">  
    <UIVisualizer ServiceId="{5452AFEA-3DF6-46BB-9177-C0B08F318025}"   
        Id="1" MenuName="Vector Visualizer"/>  
    <UIVisualizer ServiceId="{5452AFEA-3DF6-46BB-9177-C0B08F318025}"   
        Id="2" MenuName="List Visualizer"/>  
.  
.  
</AutoVisualizer>  
```  
  
 A `UIVisualizer` tarafından tanımlanan bir `ServiceId`  -  `Id` özniteliği çifti. `ServiceId`Görselleştirici paketi tarafından kullanıma sunulan hizmet GUID'dir `Id` bir hizmet birden fazla Görselleştirici sağlıyorsa görselleştiriciler ayırdetmek için kullanılan benzersiz bir tanımlayıcıdır. Yukarıdaki örnekte, iki görselleştiriciler aynı Görselleştirici hizmeti sağlar.  
  
 `MenuName` Özniteliktir Büyüteç simgesine yanında aşağı açılan menüden hata ayıklayıcı değişken pencerelerini örneğin açtıklarında kullanıcıların Görselleştirici adı olarak gördükleri:  
  
 ![UIVisualizer menü kısayol menüsünü](../debugger/media/dbg_natvis_vectorvisualizer.png "DBG_NATVIS_VectorVisualizer")  
  
 .Natvis dosyasında tanımlanan her tür açıkça görüntüleyebilmesi UI görselleştiriciler listelemeniz gerekir. Hata ayıklayıcı türleriyle kayıtlı görselleştiriciler ile eşleşecek şekilde türü girişleri Görselleştirici başvurularında eşleşir. Örneğin, giriş için aşağıdaki komutu yazın `std::vector` önceki örneğimizde UIVisualizer başvuruyor.  
  
```xml
<Type Name="std::vector&lt;int,*&gt;">  
  <UIVisualizer ServiceId="{5452AFEA-3DF6-46BB-9177-C0B08F318025}" Id="1" />  
</Type>  
```  
  
 Bellek içi bit eşlemler görüntülemek için kullanılan görüntü izleme uzantısı'nda UIVisualizer örneği görebilirsiniz: [ImageWatch](https://visualstudiogallery.msdn.microsoft.com/e682d542-7ef3-402c-b857-bbfba714f78d)  
  
### <a name="customvisualizer-element"></a>CustomVisualizer öğesi  
 `CustomVisualizer`Visual Studio'da çalışan kod görselleştirme denetlemek için yazabilirsiniz VSIX uzantısı belirten bir genişletilebilirlik noktasıdır. VSIX uzantıları yazma hakkında daha fazla bilgi için bkz: [Visual Studio SDK](../extensibility/visual-studio-sdk.md). Özel Görselleştirici yazma bir XML natvis tanımı yazma daha çok daha fazla iş, ancak hangi natvis destekler veya desteklemiyor hakkında kısıtlamalar boş. Özel görselleştiriciler hata ayıklayıcı genişletilebilirlik sorgulamak ve ayıklayıcı işlem değiştirmek veya Visual Studio diğer bölümleriyle iletişim kurmak için kullanılan API'leri, tamamını erişimi.  
  
 Kullanabileceğiniz `Condition`, `IncludeView`, ve `ExcludeView` CustomVisualizer öğelerde öznitelikleri.