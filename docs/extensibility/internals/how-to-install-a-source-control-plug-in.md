---
title: "Nasıl yapılır: kaynak denetimi eklentisi yükleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installation [Visual Studio SDK], source control plug-ins
- source control plug-ins, installing
ms.assetid: 9e2e01d9-7beb-42b2-99b2-86995578afda
caps.latest.revision: "32"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: dab9270b55f5980d36256db78db89b5e4ac186f0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-install-a-source-control-plug-in"></a>Nasıl yapılır: kaynak denetimi eklentisini yükleme
Kaynak Denetimi Eklentisi oluşturma üç adımdan oluşur:  
  
1.  Bu belge kaynak denetim eklentisi API başvuru bölümünde tanımlanan işlevlerle bir dll dosyası oluşturun.  
  
2.  Kaynak Denetim eklentisi API tarafından tanımlanan işlevler uygulayın. Zaman [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yönelik aramalarda arabirimleri ve iletişim kutuları eklenti listesinden kullanılabilir.  
  
3.  DLL uygun kayıt defteri girdileri yaparak kaydedin.  
  
## <a name="integration-with-visual-studio"></a>Visual Studio ile Tümleştirme  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]Kaynak denetimi için kaynak denetimi eklentisi API uygun Eklentiler destekler.  
  
### <a name="registering-the-source-control-plug-in"></a>Kaynak Denetim eklentisi kaydetme  
 Çalışan bir tümleşik geliştirme ortamı (IDE) kaynak denetim sisteminizle aramadan önce ilk kaynak bulmalıdır API aktarır eklentisi DLL'sini denetim.  
  
##### <a name="to-register-the-source-control-plug-in-dll"></a>Kaynak Denetim eklentisi DLL'sini kaydetmek için  
  
1.  Ürün adı alt tarafından ve ardından, şirket adı alt belirtir yazılım alt anahtarda HKEY_LOCAL_MACHINE anahtarı altında iki giriş ekleyin. Desen HKEY_LOCAL_MACHINE\Software olan\\*[Şirket adı]*\\*[Ürün adı]*\\*[entry]* = değer. İki giriş her zaman SCCServerName ve SCCServerPath olarak adlandırılır. Her normal bir dizedir.  
  
     Örneğin, şirket adınızı Microsoft ve kaynak denetimi ürününüzü ise SourceSafe, bu kayıt defteri yolu HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SourceSafe olacaktır sonra adı verilir. Bu alt anahtar ilk girişi SCCServerName, ürününüzü adlandırma bir kullanıcı tarafından okunabilen bir dizedir. İkinci, SCCServerPath, kaynak tam yolunu kontrol IDE bağlanması gereken eklentisi DLL'sini girişidir. Aşağıdaki örnek kayıt defteri girdileri sağlar:  
  
    |Örnek kayıt defteri girişi|Örnek değer|  
    |---------------------------|------------------|  
    |HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SourceSafe\SCCServerName|Microsoft Visual SourceSafe|  
    |HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SourceSafe\SCCServerPath|c:\vss\win32\ssscc.dll|  
  
    > [!NOTE]
    >  SCCServerPath eklenti SourceSafe tam yoludur. Kaynak Denetim eklentisi aynı kayıt defteri girişi yolları ancak farklı şirket ve ürün adlarını kullanır.  
  
2.  Aşağıdaki isteğe bağlı kayıt defteri girdileri eklentisi, kaynak denetimi davranışını değiştirmek için kullanılabilir. Bu girişler SccServerName ve SccServerPath olarak aynı alt anahtarda gidin.  
  
    -   Denetim Tak-bileşenini eklentisi seçim listesinde görünmesi kaynağınız istemiyorsanız HideInVisualStudioregistry giriş kullanılabilir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Bu giriş, kaynak denetimi eklenti otomatik geçiş yapmanın de etkiler. Bir olası için bu girdi, kaynak denetim eklentisi değiştirir kaynak denetimi paketi sağladığınız ancak kullanıcının kaynak denetimi için kaynak denetimi Paketi eklentisini kullanarak geçirmek daha kolay hale getirmek istediğiniz kullanılmasıdır. Kaynak denetimi paketi yüklendiğinde, eklenti gizler bu kayıt defteri girdisi ayarlar.  
  
         HideInVisualStudio bir DWORD değeri ve eklenti gizlemek için 1 veya eklenti göstermek için 0 olarak ayarlanır. Kayıt defteri girdisini görünmüyorsa, varsayılan davranışı eklenti göstermektir.  
  
    -   DisableSccManager kayıt defteri girdisini devre dışı bırakmak veya gizlemek için kullanılabilecek **başlatma \<kaynak denetim sunucusuna >** normalde altında görünen menü seçeneği **dosya**  ->   **Kaynak denetimi** alt menüsünde. Bu menüden seçerek seçeneği çağrıları [SccRunScc](../../extensibility/sccrunscc-function.md) işlevi. Kaynak Denetim eklentisi harici bir program desteklemiyor olabilir ve bu nedenle bile Gizle veya devre dışı bırakmak isteyebilirsiniz **başlatma** menü seçeneği.  
  
         DisableSccManager olan bir DWORD değeri 0 olarak ayarlanmış etkinleştirmek için **başlatma \<kaynak denetim sunucusuna >** menü seçeneği menü seçeneği devre dışı bırakmak için 1 olarak ayarlayın ve menü seçeneğinin gizlemek için 2'ye ayarlayın. Bu kayıt defteri girdisi görünmüyorsa, varsayılan davranışı menü seçeneğinin göstermektir.  
  
    |Örnek kayıt defteri girişi|Örnek değer|  
    |---------------------------|------------------|  
    |HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SourceSafe\HideInVisualStudio|1.|  
    |HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SourceSafe\DisableSccManager|1.|  
  
3.  Alt anahtar, SourceCodeControlProvider, yazılım alt HKEY_LOCAL_MACHINE anahtar altında ekleyin.  
  
     Bu alt anahtarı altında adım 1'kayıt defterinde yerleştirilen alt anahtarını temsil eden bir dize için ProviderRegKey kayıt defteri girdisini ayarlayın. Desen HKEY_LOCAL_MACHINE\SOFTWARE\SourceCodeControlProvider\ProviderRegKey olan yazılım =\\*[Şirket adı]*\\*[Ürün adı]*.  
  
     Bu alt anahtar için örnek içeriği verilmiştir.  
  
    |Kayıt defteri girdisi|Örnek değer|  
    |--------------------|------------------|  
    |HKEY_LOCAL_MACHINE\SOFTWARE\SourceCodeControlProvider\ProviderRegKey|SOFTWARE\Microsoft\SourceSafe|  
  
    > [!NOTE]
    >  Kaynak Denetim eklentisi giriş adları ve aynı alt anahtarı kullanır, ancak değeri farklı olacaktır.  
  
4.  SourceCodeControlProvider alt anahtarı altında InstalledSCCProviders adlı bir alt anahtarını oluşturmak ve ardından o alt anahtarı altında bir giriş yerleştirebilirsiniz.  
  
     Bu giriş adını sağlayıcısı (aynı SCCServerName girişi için belirtilen değer) kullanıcı tarafından okunabilen adıdır ve, bir kez daha, 1. adımda oluşturduğunuz alt değerdir. Desen HKEY_LOCAL_MACHINE\SOFTWARE\SourceCodeControlProvider\InstalledSCCProviders olan\\*[görünen ad]* yazılım =\\*[Şirket adı]* \\ *[Ürün adı]*.  
  
     Örneğin:  
  
    |Örnek kayıt defteri girişi|Örnek değer|  
    |---------------------------|------------------|  
    |HKEY_LOCAL_MACHINE\SOFTWARE\SourceCodeControlProvider\InstalledSCCProviders\Microsoft Visual SourceSafe|SOFTWARE\Microsoft\SourceSafe|  
  
    > [!NOTE]
    >  Birden fazla kaynak denetimi bu şekilde kayıtlı eklenti olabilir. Bunun nasıl [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tüm yüklü kaynak denetim eklentisi API tabanlı eklentileri bulur.  
  
## <a name="how-an-ide-locates-the-dll"></a>Nasıl bir IDE DLL bulur  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE sahip iki kaynak bulma yolları denetleyen eklentisi DLL'sini:  
  
-   Varsayılan kaynak denetimi eklenti bulmak ve sessiz bir şekilde bağlayın.  
  
-   Tüm kayıtlı kaynak denetim eklentileri alınacağı kullanıcı bunlardan birini seçer bulunamadı.  
  
 İlk şekilde DLL bulmak için giriş ProviderRegKey için HKEY_LOCAL_MACHINE\Software\SourceCodeControlProvider alt anahtarı altında IDE arar. Bu giriş değerini başka bir alt anahtarına işaret eder. IDE sonra bu ikinci alt anahtarda HKEY_LOCAL_MACHINE altında SccServerPath adlı bir girdi arar. Bu giriş değerinin IDE DLL'e işaret eder.  
  
> [!NOTE]
>  IDE DLL'leri göreli yolları (örneğin,.\NewProvider.DLL) yüklemez. DLL Dosyasının tam yolunu belirtilmelidir (örneğin, c:\Providers\NewProvider.DLL). Bu, IDE güvenlik yetkisiz veya Kimliğine bürünülen eklentisi DLL'sini yüklenmesini engelleyerek güçlendirir.  
  
 İkinci yol DLL bulmak için tüm girişleri için HKEY_LOCAL_MACHINE\Software\SourceCodeControlProvider\InstalledSCCProviders alt anahtarı altında IDE arar*.* Her girişin bir ad ve bir değere sahip. IDE kullanıcıya bu adlarının bir listesini görüntüler*.* Kullanıcı adları seçtiğinde IDE alt anahtarına noktaları seçilen adı değeri bulur. Bu alt anahtarda HKEY_LOCAL_MACHINE altında SccServerPath adlı bir girdi IDE arar. Bu giriş değerinin doğru DLL IDE işaret eder.  
  
 DLL bulma her iki yönde desteklemek ve sonuç olarak, herhangi bir önceki ayar üzerine ProviderRegKey ayarlamak, kaynak denetim eklentisi gerekir. Böylece kullanıcı kullanmak için hangi kaynak denetim eklentisi seçimine daha da önemlisi, onu kendisini InstalledSccProviders listesine eklemeniz gerekir.  
  
> [!NOTE]
>  Varsayılan kaynak denetim olarak eklenti belirli bir makinede HKEY_LOCAL_MACHINE anahtarını kullanıldığından, yalnızca bir kaynak denetimi eklenti kaydedilebilir (ancak, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] istedikleri gerçekte kullanılmak üzere hangi kaynak denetimi eklenti belirlemek kullanıcılara bir belirli çözüm). Yükleme işlemi sırasında kaynak denetimi eklenti zaten ayarlanmış olup olmadığını denetleyin; Bu durumda, kullanıcı yeni kaynak denetimi eklenti varsayılan olarak yüklenen ayarlama gerekip gerekmediğini isteyin. Yüklemeyi sırasında tüm kaynak denetim eklentilerini HKEY_LOCAL_MACHINE\SOFTWARE\SourceCodeControlProvider için ortak olan diğer kayıt defteri alt anahtarları kaldırmayın; belirli, SCC alt kaldırın.  
  
## <a name="how-the-ide-detects-version-1213-support"></a>IDE sürüm 1.2/1.3 desteğini nasıl algılar  
 Nasıl mu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] bir eklenti destekler kaynak denetim eklentisi API sürümü 1.2 ve 1.3 işlevsellik olup olmadığını algılar? Gelişmiş yetenek bildirmek için kaynak denetim eklentisi karşılık gelen işlevi uygulamalıdır.  
  
 İlk olarak, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] çağıran döndürülen değer denetler [SccGetVersion](../../extensibility/sccgetversion-function.md). 1.2 eşit veya daha büyük olmalıdır.  
  
 Ardından, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] belirli yeni özellik inceleyerek desteklenip desteklenmediğini belirler `lpSccCaps` bağımsız [SccInitialize](../../extensibility/sccinitialize-function.md).  
  
 Bu iki koşul karşılanıyorsa 1.2 ve 1.3 sürümlerinde desteklenen yeni işlevler çağrılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlarken](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)