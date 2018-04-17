---
title: C++ çekirdek yönergeleri uyarıları | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.topic: conceptual
ms.assetid: 7c83814a-f21d-4323-ad5f-13bac40d3e38
author: mblome
ms.author: mblome
manager: douge
ms.technology:
- vs-ide-code-analysis
ms.workload:
- cplusplus
ms.openlocfilehash: 1c7e5e9ee55785c1053a3d5c416529710b0b1c65
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="using-the-c-core-guidelines-checkers"></a>C++ çekirdek yönergeleri denetleyicileri kullanma
C++ çekirdek yönergeleri taşınabilir yönergeleri, kuralları ve C++ uzmanlar ve tasarımcıları tarafından oluşturulan c++ kodlama hakkında en iyi uygulamalar kümesidir. Visual Studio şu anda C++ için kendi kod Çözümleme Araçları'nın bir parçası olarak bu kurallar kümesini destekler. Çekirdek kılavuz denetleyicileri Visual Studio 2017 varsayılan olarak yüklenir ve olan [Visual Studio 2015 için NuGet paketi olarak kullanılabilir](#vs2015_corecheck).
  
## <a name="the-c-core-guidelines-project"></a>C++ çekirdek yönergeleri proje  
 Çalışan Bjarne Stroustrup ve başkaları tarafından oluşturulan, C++ çekirdek modern C++ güvenli ve verimli bir şekilde kullanmak için bir kılavuz yönergelerdir. Yönergeleri statik tür güvenliği ve kaynak güvenliği vurgulayın. Bunlar dil en hataya bölümlerini simge durumuna küçültür veya ortadan kaldırmak için yol tanımlamak ve kodunuzu daha basit hale getirmek nasıl ve daha fazla kullanıcı güvenilir bir şekilde önerir. Bu yönergeleri standart C++ Foundation tarafından korunur. Daha fazla bilgi için, bkz [C++ çekirdek yönergeleri](http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)ve C++ çekirdek yönergeleri belgelerine proje dosyalarını erişimi [GitHub](https://github.com/isocpp/CppCoreGuidelines).  
  
## <a name="enable-the-c-core-check-guidelines-in-code-analysis"></a>Kod çözümleme C++ çekirdek denetleme yönergeleri etkinleştir  
 Seçerek projenizde kod analizi etkinleştirebilirsiniz **etkinleştirmek Kod Analizi derlemede** onay kutusu **Kod Analizi** bölümünü **özellik sayfaları** iletişim kutusu için projenizi.  
  
 ![Kod çözümleme genel ayarları için özellik sayfası](../code-quality/media/cppcorecheck_codeanalysis_general.png "CPPCoreCheck_CodeAnalysis_General")  
  
 C++ çekirdek denetleme kod çözümlemesi etkinleştirildiğinde çalıştırılan varsayılan kural kümeleri için Uzantılar kurallardır. C++ çekirdek denetleme kurallar geliştirilmekte olduğundan, bazı kurallar iyi kurulan ve bazıları tüm kodu kullanılmaya hazır olmayabilir ancak yine de bilgilendirici olabilir. Kuralları iki gruba ayrılır: yayımlanmış ve Deneysel. Projeniz için özellikleri yayınlanan veya Deneysel kuralları çalıştırılıp çalıştırılmayacağını seçebilirsiniz.  
  
 ![Kod çözümleme uzantıları ayarları için özellik sayfası](../code-quality/media/cppcorecheck_codeanalysis_extensions.png "CPPCoreCheck_CodeAnalysis_Extensions")  
  
 Etkinleştirmek veya devre dışı C++ çekirdek denetleme kural kümeleri için açın **özellik sayfaları** projeniz için iletişim kutusu. Altında **yapılandırma özellikleri**, genişletin **Kod Analizi**, **uzantıları**. Açılır listede kontrol yanına **C++ çekirdek etkinleştir (Serbest)** veya **C++ çekirdek etkinleştir (Experimental)**, seçin **Evet** veya **Hayır**. Seçin **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydetmek için.  
  
## <a name="examples"></a>Örnekler  
 C++ çekirdek denetleme kuralları bulabilirsiniz sorunlardan bazıları bir örneği burada verilmiştir:  
  
```cpp  
// CoreCheckExample.cpp  
// Add CppCoreCheck package and enable code analysis in build for warnings.  
  
int main()  
{  
    int arr[10];           // warning C26494  
    int* p = arr;          // warning C26485  
  
    [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1  
    {  
        int* q = p + 1;    // warning C26481 (suppressed)  
        p = q++;           // warning C26481 (suppressed)  
    }  
  
    return 0;  
}  
```  
  
 Bu örnek, C++ çekirdek denetleme kuralları bulabilirsiniz uyarıları bazılarını gösterir:  
  
-   C26494 olan kural Type.5: her zaman bir nesne başlatılamıyor.  
  
-   C26485 olan kural Bounds.3: hiçbir dizi işaretçi decay.  
  
-   C26481 olan kural Bounds.1: işaretçi aritmetiği kullanmayın. Bunun yerine `span` kullanın.  
  
 Kod çözümleme C++ çekirdek denetleme rulesets yüklü ve bu kodu derlerken etkinleştirilirse ilk iki uyarıları çıkarılan ancak üçüncü gizlenen. Örnek kod derleme çıktısı şöyledir:  
  
```Output
1>------ Build started: Project: CoreCheckExample, Configuration: Debug Win32 ------  
1>  CoreCheckExample.cpp  
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.exe  
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.pdb (Full PDB)  
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(6): warning C26494: Variable 'arr' is uninitialized. Always initialize an object. (type.5: http://go.microsoft.com/fwlink/p/?LinkID=620421)  
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(7): warning C26485: Expression 'arr': No array to pointer decay. (bounds.3: http://go.microsoft.com/fwlink/p/?LinkID=620415)  
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========  
```  
  
C++ çekirdek yönergeleri daha iyi ve daha güvenli kod yazmanıza Yardım vardır. Ancak, bir kural veya bir profili burada uygulanan döndürmemelidir örneği varsa, doğrudan kodunda bastırmak kolaydır. Kullanabileceğiniz `gsl::suppress` algılama ve bir kuralın aşağıdaki kod bloğu içinde herhangi bir ihlali raporlama C++ çekirdek denetleme tutmak için öznitelik. Belirli kurallar gizlemek için tek tek deyimleri işaretleyebilirsiniz. Yazarak bile tüm sınırların profil gizleyebilirsiniz `[[gsl::suppress(bounds)]]` bir özel kural numarası dahil olmak üzere olmadan.  

## <a name="supported-rule-sets"></a>Kural kümeleri desteklenen
Yeni kurallar C++ çekirdek yönergeleri denetleyicisi eklendikçe önceden var olan kodu üretilen uyarı sayısı artırabilir. Hangi tür etkinleştirmek için kuralları filtrelemek için önceden tanımlanmış kural kümeleri kullanabilirsiniz. Visual Studio 2017 itibariyle sürüm 15.3, desteklenen kural kümesi şunlardır: 
  - **Sahibi işaretçi kuralları** zorunlu [kaynak yönetimi denetler ilgili sahibi<T> C++ çekirdek yönergeleri gelen](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management).

  - **Const kuralları** zorunlu [const ilişkili denetimleri C++ çekirdek yönergeleri gelen](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con-constants-and-immutability).

  - **Ham işaretçi kuralları** zorunlu [kaynak yönetimi denetler C++ çekirdek yönergeleri ilgili ham işaretçilerini](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management).

  - **Benzersiz işaretçi kuralları** zorunlu [kaynak yönetimi denetler ilgili türleri benzersiz işaretçi semantiği ile hazırladığı C++ çekirdek kılavuzları](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management).

  - **Sınırların kuralları** zorunlu [sınırları C++ çekirdek yönergeleri profilini](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile).

  - **Tür kuralları** zorunlu [yazın C++ çekirdek kılavuzlardan profili](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prosafety-type-safety-profile).


 Uyarılar yalnızca bir veya birkaç gruplarının sınırlandırmayı seçebilirsiniz. **Yerel Minimum** ve **yerel önerilen** kural kümeleri diğer PREfast denetimleri yanı sıra C++ çekirdek denetleme kuralları içerir. Kural kümeleri, Proje Özellikleri iletişim kutusunu açmak kullanılabilir görmek için seçin **kod Analysis\General**, açılır menüde açmak **kural kümesi** birleşik giriş kutusu ve çekme **birden çok kural kümesi seçin** . Visual Studio'da kural kümeleri kullanma hakkında daha fazla bilgi için bkz: [kod çözümleme kurallarını gruplandırmak için kural kümeleri kullanma](using-rule-sets-to-group-code-analysis-rules.md).

## <a name="macros"></a>Makrolar
 C++ çekirdek yönergeleri denetleyicisi kodda uyarıları tüm kategorileri bastırmak kolaylaştırmak makroları tanımlayan bir üstbilgi dosyası ile birlikte gelen:

```cpp
ALL_CPPCORECHECK_WARNINGS
CPPCORECHECK_TYPE_WARNINGS
CPPCORECHECK_RAW_POINTER_WARNINGS
CPPCORECHECK_CONST_WARNINGS
CPPCORECHECK_OWNER_POINTER_WARNINGS
CPPCORECHECK_UNIQUE_POINTER_WARNINGS
CPPCORECHECK_BOUNDS_WARNINGS
```

Bu makroları için kural kümeleri karşılık gelir ve bir boşlukla ayrılmış uyarı sayı listesi genişletin. Uygun pragma yapıları kullanarak proje için ilginç olan kurallar etkili kümesi veya kodun bir bölümünü yapılandırabilirsiniz. Aşağıdaki örnekte, Kod Analizi yalnızca sabit değiştiricileri eksik hakkında uyarır:

```cpp
#include <CppCoreCheck\Warnings.h>
#pragma warning(disable: ALL_CPPCORECHECK_WARNINGS)
#pragma warning(default: CPPCORECHECK_CONST_WARNINGS)
```

## <a name="attributes"></a>Öznitelikler
 Microsoft Visual C++ Derleyici özniteliği gizlemek için GSL bir sınırlı destek vardır.
İfade ve bir işlev içinde blok deyimleri uyarıları gizlemek için kullanılabilir.

```cpp
// Supress only warnings from the 'r.11' rule in expression.
[[gsl::suppress(r.11)]] new int;

// Supress all warnings from the 'r' rule group (resource management) in block.
[[gsl::suppress(r)]]
{ 
    new int; 
}

// Suppress only one specific warning number.
// For declarations, you may need to use the surrounding block.
// Macros are not expanded inside of attributes.
// Use plain numbers instead of macros from the warnings.h.
[[gsl::suppress(26400)]]
{
    int *p = new int;
}
```  

## <a name="suppressing-analysis-by-using-command-line-options"></a>Komut satırı seçeneklerini kullanarak Analiz gizleme
 #Pragmas yerine bir proje veya tek bir dosya için uyarıları bastırma dosyanın özellik sayfasında komut satırı seçeneklerini kullanabilirsiniz. Örneğin, uyarıyı devre dışı bırakmak için bir dosya için 26400:
 
 1) Dosyayı sağ tıklatın **Çözüm Gezgini**

 2) Seçin **özellikleri | C / C ++ | Komut satırı**

 3) İçinde **ek seçenekler** penceresinde eklemek `/wd26400`.

 Komut satırı seçeneği geçici olarak bir dosya için tüm kod analizi belirterek devre dışı bırakmak için kullanabileceğiniz `/analyze-`. Bu uyarı üretecektir *D9025 geçersiz kılma '/ analyze' ile ' / analyze-'*, hangi anımsatmak Kod Analizi daha sonra yeniden etkinleştirmek için.

 ## <a name="corecheck_per_file"></a> Belirli bir proje dosyalarında C++ çekirdek yönergeleri denetleyicisi etkinleştirme
Bazen odaklanmış Kod Analizi ve hala Dengeleme Visual Studio IDE yararlı olabilir. Büyük projeler için derleme zamanında kaydetmek ve filtre sonuçları kolaylaştırmak için kullanılan bir örnek senaryo aşağıdadır.
1.  Komut kabuğu'nda ayarlanmış `esp.extension` ve `esp.annotationbuildlevel` ortam değişkenleri.
2.  Visual Studio bu değişkenleri devralmak için komut kabuğu'ndan başlatın.
3.  Projenize yüklemek ve özelliklerini açın.
4.  Kod çözümleme etkinleştirmek, uygun kural kümeleri çekme, ancak kod çözümleme uzantıları etkinleştirmeyin.
5.  C++ çekirdek yönergeleri denetleyicisi ile çözümlemek ve özelliklerini açmak için istediğiniz dosyasına gidin.
6.  Seçin **C / C ++ \Command satırı seçeneklerini** ve Ekle `/analyze:plugin EspXEngine.dll`
7.  Önceden derlenmiş üst bilgi kullanımını devre dışı bırakmak (**C / C ++ \Precompiled üstbilgileri**). Bu, çünkü uzantıları altyapısı önceden derlenmiş başlığından kendi iç bilgileri okuma girişimi ve varsayılan proje seçenekleri ile ikinci derlenen, yeniden uyumlu olmayacaktır gereklidir.
8.  Projeyi yeniden oluşturun. Ortak PREFast denetimleri tüm dosyalarda çalıştırmanız gerekir. C++ çekirdek yönergeleri denetleyicisi varsayılan olarak etkin olmadığından, yalnızca kullanmak üzere yapılandırıldığı dosyasını çalıştırmanız gerekir.

## <a name="how-to-use-the-c-core-guidelines-checker-outside-of-visual-studio"></a>Visual Studio dışında C++ çekirdek yönergeleri Denetleyicisi'ni kullanma
C++ çekirdek yönergeleri denetimleri otomatik derlemelerde kullanabilirsiniz.

### <a name="msbuild"></a>MSBuild
 Yerel Kod Analizi denetleyicisi (PREfast) özel hedefleri dosyaları tarafından MSBuild ortamına tümleşiktir. Proje özellikleri etkinleştirmek ve (hangi PREfast üzerinde temel alır) C++ çekirdek yönergeleri denetleyicisi ekleyin:

 ```xml
  <PropertyGroup>
    <EnableCppCoreCheck>true</EnableCppCoreCheck>
    <CodeAnalysisRuleSet>CppCoreCheckRules.ruleset</CodeAnalysisRuleSet>¬¬
    <RunCodeAnalysis>true</RunCodeAnalysis>
  </PropertyGroup>
```
Bu özellikleri Microsoft.Cpp.targets dosyasının almadan eklediğinizden emin olun. Özel kural kümeleri seçin veya özel bir kural kümesini oluşturun veya diğer PREfast denetimleri içeren varsayılan kural kümesini kullanın.

Olarak aynı yaklaşımı kullanarak, yalnızca belirtilen dosyalar için C++ çekirdek Denetleyicisi'ni çalıştırabilirsiniz [daha önce açıklanan](#coreckeck_per_file), ancak MSBuild dosyalarını kullanma. Ortam değişkenleri kullanılarak ayarlanabilir `BuildMacro` öğe:

```xml
<ItemGroup>
    <BuildMacro Include="Esp_AnnotationBuildLevel">
      <EnvironmentVariable>true</EnvironmentVariable>
      <Value>Ignore</Value>
    </BuildMacro>
    <BuildMacro Include="Esp_Extensions">
      <EnvironmentVariable>true</EnvironmentVariable>
      <ValueCppCoreCheck.dll</Value>
    </BuildMacro>
</ItemGroup>
```

Proje dosyası değiştirmek istemiyorsanız, komut satırında özellikler geçirebilirsiniz:

```cmd
msbuild /p:EnableCppCoreCheck=true /p:RunCodeAnalysis=true /p:CodeAnalysisRuleSet=CppCoreCheckRules.ruleset ...
```

### <a name="non-msbuild-projects"></a>MSBuild olmayan projeleri
MSBuild üzerinde kullanmaz bir yapı sistemi kullanıyorsanız denetleyicisi çalıştırmaya devam ancak (gelecekte desteklenecek kesin değildir) kod çözümleme altyapısı yapılandırması bazı içyüzü hakkında bilgi edinmek gerekir.

Birkaç ortam değişkenlerini ayarlama ve derleyici için uygun komut satırı seçenekleri kullanmak gerekir. Yok böylece derleyici için belirli yollar için arama yapın, dizinleri, vb. dahil "yerel Araçları komut istemi" ortamı altında çalışması iyidir.

1.  **Ortam değişkenleri**
  - `set esp.extensions=cppcorecheck.dll` Bu C++ çekirdek yönergeleri modülünü yüklemek için altyapısı bildirir.
  - `set esp.annotationbuildlevel=ignore` SAL ek açıklamaları işleyen mantığı, devre dışı bırakır. Ek açıklamalar Kod Analizi C++ çekirdek yönergeleri Denetleyicisi'nde etkilemeyen henüz kendi işleme alır (bazen çok zaman) süresi. Bu ayar isteğe bağlıdır, ancak önemle önerilir.
  - `set caexcludepath=%include%` Standart üstbilgilerinde yangın uyarılar devre dışı bırakmanız önerilir. Daha fazla yollarını burada, örneğin projenizdeki ortak üst bilgileri yolunu ekleyebilirsiniz.
2.  **Komut satırı seçenekleri**
  - `/analyze`  Kodunu analiz (aynı zamanda kullanmayı / analyze: yalnızca ve / analyze: sessiz).
  - `/analyze:plugin EspXEngine.dll` Bu seçenek kod çözümleme uzantıları altyapısı PREfast yükler. Bu altyapı sırayla C++ çekirdek yönergeleri denetleyicisi yükler.



## <a name="use-the-guideline-support-library"></a>Kullanım Kılavuzu destek kitaplığı  
 Kılavuz destek kitaplığı çekirdek yönergelere yardımcı olmak için tasarlanmıştır. GSL ile daha güvenli alternatifler hataya yatkın yapıları değiştirmenizi sağlayan tanımlarını içerir. Örneğin, yerine bir `T*, length` parametrelerle çiftinin `span<T>` türü. GSL şu adresten edinilebilir [ http://www.nuget.org/packages/Microsoft.Gsl ](http://www.nuget.org/packages/Microsoft.Gsl). Kitaplık kaynaklarını görüntülemek, yorum yapmak veya katkıda açık kaynak olduğundan. Proje bulunabilir [ https://github.com/Microsoft/GSL ](https://github.com/Microsoft/GSL).

 ## <a name="vs2015_corecheck"></a> Visual Studio 2015 projelerinde C++ çekirdek denetleme yönergeleri kullanın  
  Visual Studio 2015 kullanıyorsanız, C++ çekirdek denetleme Kod Analizi kural kümeleri varsayılan olarak yüklenmez. Kod çözümleme C++ çekirdek denetleme araçları Visual Studio 2015'te etkinleştirmeden önce bazı ek adımlar gerçekleştirmeniz gerekir. Microsoft, bir Nuget paketi kullanarak, Visual Studio 2015 projeleri için destek sağlar. Microsoft.CppCoreCheck adlı paket ve adresten edinilebilir [ http://www.nuget.org/packages/Microsoft.CppCoreCheck ](http://www.nuget.org/packages/Microsoft.CppCoreCheck). Bu paket, yüklü en az Visual Studio 2015 güncelleştirme 1 ile sahip gerektirir.  
  
 Paketi, başka bir paketi bir bağımlılık olarak bir salt üstbilgi kılavuz destek kitaplığı (GSL) de yükler. GSL github'da da kullanılabilir [ https://github.com/Microsoft/GSL ](https://github.com/Microsoft/GSL).  

 Kod çözümleme kurallarını yüklenen yöntemi nedeniyle, Visual Studio 2015 içinde denetlemek istediğiniz her C++ projesine Microsoft.CppCoreCheck NuGet paketini yüklemeniz gerekir.  
  
#### <a name="to-add-the-microsoftcppcorecheck-package-to-your-project-in-visual-studio-2015"></a>Projeniz Visual Studio 2015'te Microsoft.CppCoreCheck paketini eklemek için  
  
1.  İçinde **Çözüm Gezgini**, pakete eklemek istediğiniz çözüm projenizin bağlam menüsünü açmak için sağ tıklatın. Seçin **NuGet paketlerini Yönet** açmak için **NuGet Paket Yöneticisi**.  
  
2.  İçinde **NuGet Paket Yöneticisi** penceresinde, Microsoft.CppCoreCheck arayın.  
  
     ![Nuget Paket Yöneticisi penceresi gösterir CppCoreCheck paket](../code-quality/media/cppcorecheck_nuget_window.PNG "CPPCoreCheck_Nuget_Window")  
  
3.  Microsoft.CppCoreCheck paketi seçin ve ardından **yükleme** düğmesi kuralları projenize ekleyin.  
  
 NuGet paketini projenize projenizde kod analizi etkinleştirdiğinizde çağrılan bir ek MSBuild .targets dosyasında ekler. Bu .targets dosyasında C++ çekirdek denetleme kuralları için Visual Studio kod analizi aracı ek bir uzantısı olarak ekler. Paketi yüklendiğinde, etkinleştirme veya devre dışı bırakılmış ve Deneysel kuralları özellik sayfaları iletişim kutusunu kullanabilirsiniz.  
  
