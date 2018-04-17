---
title: 'Nasıl yapılır: Visual Studio uzantıları için kural tabanlı UI bağlam kullanın | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 8dd2cd1d-d8ba-49b9-870a-45acf3a3259d
author: gregvanl
ms.author: gregvanl
ms.workload:
- vssdk
ms.openlocfilehash: 8597c413c899b54e61e848649c3c524cbdb20724
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-use-rule-based-ui-context-for-visual-studio-extensions"></a>Nasıl yapılır: Visual Studio uzantıları için kural tabanlı UI bağlam kullanın
Visual Studio VSPackages belirli zaman yüklenmesini sağlar iyi bilinen <xref:Microsoft.VisualStudio.Shell.UIContext>s etkinleşir. Ancak, bu UI bağlamları düzey, hiçbir tercih uzantısı yazarlar bırakarak çok iyi değildir ancak noktasından önce etkinleştirir kullanılabilir bir UI bağlamı seçmek için gerçekten yüklemek için VSPackage istedikleri. İyi bilinen UI bağlamları listesi için bkz: <xref:Microsoft.VisualStudio.Shell.KnownUIContexts>.  
  
 Paketler yüklenirken bir performans etkisi olabilir ve gerekli olan daha çabuk yüklenirken en iyi yöntem değildir. Visual Studio 2015 kural tabanlı UI bağlamı, uzantısı yazarların altında çalışacağı bir kullanıcı Arabirimi bağlamı etkinleştirilir ve ilişkili VSPackages yüklenen kesin koşullarını tanımlamak bir mekanizma kavramı sunmuştur.  
  
## <a name="rule-based-ui-context"></a>Kural tabanlı UI bağlamı  
 Yeni kullanıcı Arabirimi bağlamında (GUID) "Kuralı" oluşur ve bir veya daha fazla "terimi" başvuran bir Boole ifadesi mantıksal birlikte "ve", "veya", "değil" işlemleri. "Koşulları" çalışma zamanında dinamik olarak değerlendirilir ve ifade koşulları değişiklikleri her yeniden değerlendirilir. İfade doğru olarak değerlendirildiğinde ilişkili UI bağlam etkinleştirilir. Aksi takdirde, UI bağlam de-activated olur.  
  
 Kural tabanlı UI bağlam çeşitli şekillerde kullanılabilir:  
  
1.  Komutlar ve aracı windows görünürlük kısıtlamalarını belirtin. UI bağlam kural yerine getirilene kadar windows komutları/araçları gizleyebilirsiniz.  
  
2.  Otomatik yükü sınırlamaları: otomatik yükleme paketleri yalnızca kural karşılandığında  
  
3.  Gecikmeli görevi: Belirtilen geçtikten ve kural hala karşılanır kadar yüklenirken gecikme.  
  
 Mekanizması tüm Visual Studio uzantısı tarafından kullanılıyor olabilir.  
  
## <a name="create-a-rule-based-ui-context"></a>Bir kural tabanlı UI bağlam oluşturma  
 Yalnızca ".config" uzantılı dosyalar için geçerli bir menü komutu sunar TestPackage adlı bir uzantı olduğunu varsayalım. VS2015 önce TestPackage yüklemek için en iyi seçenek olan zaman <xref:Microsoft.VisualStudio.Shell.KnownUIContexts.SolutionExistsAndFullyLoadedContext%2A> UI bağlam etkinleştirilmediği. Yüklenen çözümü .config dosyasına bile içermeyebilir beri bu verimli değildir. Bize bakın kural tabanlı UI bağlam yalnızca bir dosya açıldığında .config uzantısına sahip bir kullanıcı Arabirimi bağlamı etkinleştirmek için kullanılabilir nasıl seçilidir ve bu UI bağlam etkinleştirildiğinde TestPackage yükleyin.  
  
1.  Yeni bir UIContext GUID tanımlayın ve VSPackage sınıfına ekleyin <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> ve <xref:Microsoft.VisualStudio.Shell.ProvideUIContextRuleAttribute>.  
  
     Örneğin, yeni UIContext varsayalım "UIContextGuid" olan eklenecek. Oluşturulan GUID (araçları tıklatarak bir GUID oluşturabilirsiniz -> GUID oluşturun) "8B40D5E2-5626-42AE-99EF-3DD1EFF46E7B" değil. Ardından aşağıdaki ekleyin, paket sınıfı içinde:  
  
    ```csharp  
    public const string UIContextGuid = "8B40D5E2-5626-42AE-99EF-3DD1EFF46E7B";  
    ```  
  
     Öznitelikler için aşağıdakileri ekleyin: (Bu öznitelikler ayrıntılarını daha sonra verilecektir)  
  
    ```csharp  
    [ProvideAutoLoad(TestPackage.UIContextGuid)]      
    [ProvideUIContextRule(TestPackage.UIContextGuid,  
        name: "Test auto load",   
        expression: "DotConfig",  
        termNames: new[] { "DotConfig" },  
        termValues: new[] { "HierSingleSelectionName:.config$" })]  
    ```  
  
     Bu meta verileri yeni UIContext GUID (8B40D5E2-5626-42AE-99EF-3DD1EFF46E7B) ve tek bir terim, "DotConfig" başvuran bir ifade tanımlayın. Geçerli seçim etkin olan hiyerarşi içinde normal ifade deseni ile eşleşen bir ada sahip olduğunda "DotConfig" terimi true olarak değerlendirilir "\\.config$" (".config" ile biten). (Varsayılan) değeri hata ayıklama için yararlı kuralı için isteğe bağlı bir ad tanımlar.  
  
     Öznitelik değerlerini daha sonra derleme zamanı sırasında oluşturulan pkgdef eklenir.  
  
2.  TestPackage'nın komutlar için VSCT dosyasında "DynamicVisibility" bayrağı uygun komutları ekleyin:  
  
    ```xml  
    <CommandFlag>DynamicVisibility</CommandFlag>  
    ```  
  
3.  VSCT görünürlüğe bölümünde yeni UIContext #1'de tanımlanan GUID için uygun komutları bağlayın:  
  
    ```xml  
    <VisibilityConstraints>   
        <VisibilityItem guid="guidTestPackageCmdSet" id="TestId"  context="guidTestUIContext"/>   
    </VisibilityConstraints>  
    ```  
  
4.  Simgeler bölümünde UIContext tanımını ekleyin:  
  
    ```xml  
    <GuidSymbol name="guidTestUIContext" value="{8B40D5E2-5626-42AE-99EF-3DD1EFF46E7B}" />  
    ```  
  
     Şimdi, bağlam menüsü komutlarını *.config dosyaları için yalnızca Çözüm Gezgini'nde seçilen öğe bir ".config" dosyasıdır ve bu komutlardan birini seçilene kadar paketi yüklü değil görünür.  
  
 Ardından, bir hata ayıklayıcısı paket yalnızca zaman kendisine bekliyoruz yükler onaylamak için kullanalım. TestPackage hata ayıklamak için:  
  
1.  Bir kesme noktası kümesinde <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> yöntemi.  
  
2.  TestPackage derleyin ve hata ayıklamayı Başlat.  
  
3.  Bir proje oluşturun veya açın.  
  
4.  .Config dışında uzantılı bir dosya seçin. Kesme noktası isabet değil.  
  
5.  App.Config dosyasını seçin.  
  
 TestPackage yükler ve kesme noktasında durur.  
  
## <a name="adding-more-rules-for-ui-context"></a>UI bağlamı için daha fazla kural ekleme  
 UI bağlam kuralları Boole ifadeleri olduğundan, bir kullanıcı Arabirimi bağlam için daha kısıtlı bir kuralı ekleyebilirsiniz. Örneğin, yukarıdaki UI bağlamında, kural yalnızca bir proje ile bir çözüm ne zaman yüklendi geçerli olduğunu belirtebilirsiniz. Bu şekilde, komutları, ".config" dosyasını yedekleyin açarsanız, projesinin bir parçası olarak değil bir tek başına dosya olarak görünmez.  
  
```csharp  
[ProvideAutoLoad(TestPackage.UIContextGuid)]      
[ProvideUIContextRule(TestPackage.UIContextGuid,    
    name: "Test auto load",  
    expression: "(SingleProject | MultipleProjects) & DotConfig",    
    termNames: new[] { "SingleProject", "MultipleProjects","DotConfig" },     
    termValues: new[] { VSConstants.UICONTEXT_SolutionHasSingleProject_string , VSConstants.UICONTEXT_SolutionHasMultipleProjects_string , "HierSingleSelectionName:.config$" })]  
```  
  
 Artık üç koşulları ifadesine başvuruyor. İlk iki terimin "SingleProject" ve "MultipleProjects" (GUID'ler) olarak bilinen diğer UI bağlamları bakın. Üçüncü, "DotConfig" kural tabanlı UI daha önce tanımladığımız bağlamı bir terimdir.  
  
## <a name="delayed-activation"></a>Gecikmeli etkinleştirme  
 Kurallar, bir isteğe bağlı "gecikme" olabilir. Gecikme süresini milisaniye cinsinden belirtilir. Varsa, gecikme etkinleştirme veya devre dışı bırakma bu zaman aralığına göre Gecikmeli için bir kural UI içeriğinin neden olur. Kural değişiklikleri önceki gecikme aralığı yedeklerseniz, hiçbir şey olmaz. Bu mekanizma "başlatma adımları - zamanlayıcılar üzerinde güvenmek veya boşta bildirimleri için kaydediliyor olmadan özellikle tek seferlik başlatma basamaklandırmak için" kullanılabilir.  
  
 Örneğin, 100 milisaniyede bir gecikme için test yük kuralınız belirtebilirsiniz:  
  
```csharp  
[ProvideAutoLoad(TestPackage.UIContextGuid)]  
[ProvideUIContextRule(TestPackage.UIContextGuid,   
    name: "Test auto load",  
    expression: "DotConfig",   
    termNames: new[] { "DotConfig" },  
    termValues: new[] { "HierSingleSelectionName:.config$" },   
    delay: 100)]  
```  
  
## <a name="term-types"></a>Terim türleri  
 Terim desteklenen çeşitli türleri şunlardır:  
  
|||  
|-|-|  
|{nnnnnnnn-nnnn-nnnn-nnnn-nnnnnnnnnnnn}|GUID bir UI bağlamına başvuruyor. UI bağlam etkin ve false Aksi durumda olduğunda terimi true olur.|  
|HierSingleSelectionName:\<düzeni >|Terim etkin olan hiyerarşi seçim tek bir öğedir ve seçilen öğenin adını "düzeni" tarafından verilen .net normal ifadeyle eşleşen olduğunda true olur.|  
|UserSettingsStoreQuery:\<sorgu >|"sorgu" sıfır olmayan bir değere değerlendirilmelidir kullanıcı ayarları deposu içine tam yolu temsil eder. Sorgu "toplama" ve "propertyName" en son eğik çizgi ayrılır.|  
|ConfigSettingsStoreQuery:\<sorgu >|"sorgu" sıfır olmayan bir değere değerlendirilmelidir yapılandırma ayarları depolama alanı içine tam yolu temsil eder. Sorgu "toplama" ve "propertyName" en son eğik çizgi ayrılır.|  
|ActiveProjectFlavor:\<projectTypeGuid >|Şu anda seçili proje özellikli her terim true olur (toplanan) ve verilen proje türü GUID eşleşen bir özellik vardır.|  
|ActiveEditorContentType:\<contentType >|Seçili dosyayı bir metin düzenleyicisi verilen içerik türüne sahip olduğunda terimi true olur.|  
|ActiveProjectCapability:\<ifade >|Etkin proje özellikleri sağlanan ifade eşleştiğinde true bir terimdir. Bir ifade VB şöyle olabilir &#124; CSharp|  
|SolutionHasProjectCapability:\<ifade >|Yukarıdaki benzer; ancak terim olduğunda true ifadeyle eşleşen tüm yüklenen proje çözümü vardır.|  
|SolutionHasProjectFlavor:\<projectTypeGuid >|Bir çözüm (toplanan) özellikli proje ve verilen proje türü GUID eşleşen bir özellik sahip her terim true olur.|


  
## <a name="compatibility-with-cross-version-extension"></a>Sürümler arası uzantısı ile uyumluluk  
 Kuralı tabanlı UI bağlamları Visual Studio 2015'te yeni bir özelliktir ve önceki sürümleri için bağlantı noktası kurulmuş değil. Bu, Visual Studio 2013'te otomatik olarak yüklenir ve önceki olması gerekir, ancak otomatik-Visual Studio 2015'te yüklenmesini önlemek için kurala dayalı UI bağlamları yararlanabilir Visual Studio'nun birden çok sürümünü hedef uzantıları/paketleri ile ilgili bir sorun oluşturur.  
  
 Gibi paketlerin desteklemek için kayıt defterinde AutoLoadPackages girdileri artık Visual Studio 2015 ve üzeri giriş atlanacağını belirtmek için değeri alanına bir bayrak sağlayabilir. Bu bayrak seçeneğine ekleyerek yapılabilir <xref:Microsoft.VisualStudio.Shell.PackageAutoLoadFlags>. VSPackages şimdi ekleyebilirsiniz **SkipWhenUIContextRulesActive** için seçenek kendi <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> giriş dikkate Visual Studio 2015 ve sonraki belirtmek için öznitelik.  
  
## <a name="extensible-ui-context-rules"></a>Genişletilebilir UI bağlam kuralları  
 Bazı durumlarda, paketleri statik UI bağlam kuralları kullanamazsınız. Örneğin, komut durumu, içeri aktarılan MEF sağlayıcıları tarafından desteklenen Düzenleyicisi türlerine dayanan şekilde genişletilebilirlik destekleyen bir paket olduğunu varsayalım. Geçerli düzenleme türü destekleyen bir uzantı ise komutu etkinleştirilir. Koşulları bağlı olarak hangi MEF uzantıları kullanılabilir değişeceğinden beri bu gibi durumlarda statik UI bağlam kural paket kullanamazsınız.  
  
 Gibi paketlerin desteklemek için sabit kodlanmış ifade kurala dayalı UI bağlamları desteği "*", katılması ile tüm aşağıdaki koşulları gösterir veya. Bu bilinen bir kural UI bağlam temel tanımlamak ana paket için verir ve bu bağlamda komutu durumuna bağlayın. Daha sonra ana paketi için hedeflenen tüm MEF uzantısı başka koşullar veya ana ifade etkilemeden destekleyen düzenleyiciler için şartlarını ekleyebilirsiniz.  
  
 Oluşturucusu <xref:Microsoft.VisualStudio.Shell.ProvideExtensibleUIContextRuleAttribute.%23ctor%2A> belgelerine Genişletilebilir UI bağlam kuralları sözdizimi gösterilmektedir.