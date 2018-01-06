---
title: "Proje C++ hata ayıklama yapılandırması için ayarları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCDebugSettings.WebBrowser.DebuggerType
- VC.Project.IVCGPUDebugPageObject.EnvironmentMerge
- VC.Project.VCDebugSettings.SymbolPath
- VC.Project.IVCClusterDebugPageObject.ApplicationCommand
- VC.Project.IVCRemoteDebugPageObject.WorkingDirectory
- VC.Project.VCDebugSettings.DebuggerType
- VC.Project.IVCLocalDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCRemoteDebugPageObject.SQLDebugging
- VC.Project.IVCRemoteDebugPageObject.Remote
- VC.Project.IVCGPUDebugPageObject.CommandArguments
- VC.Project.VCDebugSettings.CommandArguments
- VC.Project.IVCClusterDebugPageObject.MPIRunWorkingDirectory
- VC.Project.IVCLocalDebugPageObject.SQLDebugging
- VC.Project.IVCWebSvcDebugPageObject.HttpUrl
- VC.Project.IVCLocalDebugPageObject.WorkingDirectory
- VC.Project.IVCLocalDebugPageObject.CommandArguments
- VC.Project.IVCClusterDebugPageObject.MPIRunCommand
- VC.Project.IVCGPUDebugPageObject.WorkingDirectory
- VC.Project.IVCWebSvcDebugPageObject.DebuggerType
- VC.Project.IVCRemoteDebugPageObject.CommandArguments
- VC.Project.IVCRemoteDebugPageObject.DebuggerType
- VC.Project.IVCLocalDebugPageObject.GPUBreakOnAllThreads
- VC.Project.IVCRemoteDebugPageObject.RemoteMachine
- VC.Project.IVCClusterDebugPageObject.MPIRunArguments
- VC.Project.IVCClusterDebugPageObject.MPIAcceptFilter
- VC.Project.IVCGPUDebugPageObject.RemoteConnection
- VC.Project.VCDebugSettings.PDBPath
- VC.Project.IVCRemoteDebugPageObject.DeploymentDirectory
- VC.Project.VCDebugSettings.SQLDebugging
- VC.Project.VCDebugSettings.RemoteCommand
- VC.Project.IVCClusterDebugPageObject.ShimCommand
- VC.Project.IVCLocalDebugPageObject.Command
- VC.Project.IVCRemoteDebugPageObject.GPUBreakOnAllThreads
- VC.Project.IVCLocalDebugPageObject.Attach
- VC.Project.VCDebugSettings.Command
- VC.Project.IVCRemoteDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCRemoteDebugPageObject.RemoteCommand
- VC.Project.IVCClusterDebugPageObject.ApplicationArguments
- VC.Project.IVCLocalDebugPageObject.Environment
- VC.Project.IVCGPUDebugPageObject.DeploymentDirectory
- VC.Project.IVCLocalDebugPageObject.EnvironmentMerge
- VC.Project.VCDebugSettings.Environment
- VC.Project.IVCGPUDebugPageObject.BreakpointBehavior
- VC.Project.IVCLocalDebugPageObject.DebuggerType
- VC.Project.VCDebugSettings.WebBrowser.WebBrowserDebuggerHttpUrl
- VC.Project.IVCWebSvcDebugPageObject.SQLDebugging
- VC.Project.IVCGPUDebugPageObject.AcceleratorType
- VC.Project.IVCGPUDebugPageObject.Environment
- VC.Project.VCDebugSettings.RemoteMachine
- VC.Project.IVCGPUDebugPageObject.AdditionalFilesToDeploy
- VC.Project.VCDebugSettings.WorkingDirectory
- vs.debug.builds
- VC.Project.VCDebugSettings.Attach
- VC.Project.VCDebugSettings.HttpUrl
- VC.Project.IVCClusterDebugPageObject.MPIAcceptMode
- VC.Project.IVCGPUDebugPageObject.Attach
- VC.Project.IVCRemoteDebugPageObject.AdditionalFiles
- VC.Project.IVCGPUDebugPageObject.Command
- VC.Project.VCDebugSettings.Remote
- VC.Project.IVCRemoteDebugPageObject.Attach
- VC.Project.VCDebugSettings.EnvironmentMerge
- VC.Project.IVCGPUDebugPageObject.MachineName
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- DEBUG linker option
- -PDB linker option
- -Zl compiler option [C++]
- /DEBUG linker option
- /PDBSTRIPPED linker option
- /MAPINFO linker option
- -Zd compiler option [C++]
- -DEBUG linker option
- MAPINFO linker option
- /ZI compiler option [C++]
- ZI compiler option [C++]
- Z7 compiler option [C++]
- debugging [C++], debugger settings
- project settings [Visual Studio], debug configurations
- mapfiles, project settings
- debug configurations, C++
- project settings [Visual Studio]
- /PDB linker option
- -PDBSTRIPPED linker option
- debug builds, project settings
- PDB linker option
- projects [Visual Studio], debug configurations
- project configurations, debug
- Zd compiler option [C++]
- MAP linker option
- /Z7 compiler option [C++]
- .pdb files, debug build project settings
- -MAP linker option
- -MAPINFO linker option
- /Zd compiler option [C++]
- PDBSTRIPPED linker option
- -Z7 compiler option [C++]
- pdb files, debug build project settings
- /MAP linker option
ms.assetid: 860c7f13-a108-4fe5-8fca-d235cd3ca1cb
caps.latest.revision: "49"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cbb7e773c3c2cbb21ae4ac8d93f695601e8a3663
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="project-settings-for-a-c-debug-configuration"></a>C++ hata ayıklama yapılandırması proje ayarları
Bir C veya Visual C++ hata ayıklama yapılandırması proje ayarları değiştirebileceğiniz **özellik sayfaları** anlatıldığı gibi iletişim kutusu, [nasıl yapılır: ayarlama hata ayıklama ve dağıtım yapılandırmalarını](../debugger/how-to-set-debug-and-release-configurations.md). Aşağıdaki tablolarda hata ayıklayıcı gizlilikle ilgili ayarların nerede bulacağını Göster **özellik sayfaları** iletişim kutusu.  
  
> [!WARNING]
>  Hata ayıklama proje ayarlarında **yapılandırma özellikleri/hata ayıklama** kategori UWP uygulamaları ve C++ ile yazılmış bileşenleri için farklıdır. Bkz: [(VB, C#, C++ ve XAML) bir hata ayıklama oturumu Başlat](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md).  
  
 Kullanmak için hangi hata ayıklayıcı belirtin **başlatmak için hata ayıklayıcı** liste kutusu. Tercih ettiğiniz hangi özelliklerin görünür etkiler.  
  
 Her hata ayıklama özellik ayarı otomatik olarak yazılmış ve "kullanıcı başına" dosyasına kaydedilir (. vcxproj.user) çözümünüzü kaydedin olduğunda, çözümünüz için.  
  
## <a name="configuration-properties-folder-debugging-category"></a>Yapılandırma özellikleri klasörü (hata ayıklama kategori)  
  
|**Ayarı**|**Açıklama**|  
|-----------------|---------------------|  
|**Başlatmak için hata ayıklayıcı**|, Aşağıdaki seçenekleri çalıştırmak için hata ayıklayıcı belirtir:<br /><br /> -   **Yerel Windows hata ayıklayıcı**<br />-   **Uzak Windows hata ayıklayıcı**<br />-   **Web tarayıcısı hata ayıklayıcı**<br />-   **Web hizmeti hata ayıklayıcı**|  
|**Komut** (yerel Windows hata ayıklayıcı)|Hata ayıklama yaptığınız programı yerel bilgisayarda başlatma komutunu belirtir.|  
|**Uzak komuttan** (uzak Windows hata ayıklayıcı)|Uzak bilgisayarda .exe yolu. Yalnızca uzak makinede girersiniz yolunu girin.|  
|**Komut bağımsız değişkenleri** (yerel Windows hata ayıklayıcı ve uzak Windows hata ayıklayıcı)|-Daha önce belirtilen komut bağımsız değişkenlerini belirtir.<br /><br /> Bu kutuya aşağıdaki yeniden yönlendirme işleçleri kullanabilirsiniz:<br /><br /> < `file`<br /> Stdin dosyasından okur.<br /><br /> > `file`<br /> STDOUT dosyasına yazar.<br /><br /> >> `file`<br /> STDOUT dosyasına ekler.<br /><br /> 2> `file`<br /> Stderr dosyasına yazar.<br /><br /> 2>> `file`<br /> Stderr dosyasına ekler.<br /><br /> 2> &1<br /> Stdout (1) aynı konuma (2) stderr çıktısı gönderir.<br /><br /> 1> &2<br /> Stderr (2) ile aynı konumda STDOUT (1) çıkış gönderir.<br /><br /> Çoğu durumda bu işleçlere yalnızca konsol uygulamaları için geçerlidir.|  
|**Çalışma dizini**|EXE bulunduğu proje dizinine göre ayıklanacak programın çalışma dizinini belirtir. Burayı boş bırakırsanız, çalışma dizini proje dizindir. Uzaktan hata ayıklama için proje dizininin uzak sunucuda olacaktır.|  
|**Attach** (yerel Windows hata ayıklayıcı ve uzak Windows hata ayıklayıcı)|Başlat veya uygulamaya eklemek belirtir. Varsayılan ayar Hayır.|  
|**Uzak sunucu adını** (uzak Windows hata ayıklayıcı)|Bir uygulamada hata ayıklamak istediğiniz bilgisayarın (dışında sizin hesabınız) adını belirtir.<br /><br /> RemoteMachine derleme makro bu özellik değerine ayarlanır; Daha fazla bilgi için bkz: [derleme komutları ve Özellikler makroları](/cpp/ide/common-macros-for-build-commands-and-properties).|  
|**Bağlantı** (uzak Windows hata ayıklayıcı)|Uzaktan hata ayıklama için standart ve doğrulaması yok bağlantı türleri arasında geçiş yapmanızı sağlar. Bir uzak bilgisayar adı belirtmeniz **uzak sunucu adı** kutusu. Bağlantı türleri şunlardır:<br /><br /> -   **Windows kimlik doğrulaması ile uzaktan**<br />-   **Kimlik doğrulaması ile uzaktan**<br /><br /> **Not** Hayır kimlik doğrulaması ile uzaktan hata ayıklama bırakın uzak bilgisayarda güvenlik ihlallerine karşı savunmasız. Windows kimlik doğrulaması modunu daha güvenlidir.<br /><br /> Daha fazla bilgi için bkz: [uzaktan hata ayıklama Kurulumu](../debugger/remote-debugging.md).|  
|**HTTP URL** (Web hizmeti hata ayıklayıcı ve Web tarayıcısı hata ayıklayıcı)|Hata ayıklama yaptığınız proje bulunduğu URL'yi belirtir.|  
|**Hata ayıklayıcı türü**|Kullanılacak hata ayıklayıcı türünü belirtir: **yalnızca yerel**, **yalnızca yönetilen**, **yalnızca GPU**, **karma**, **otomatik**(varsayılan) veya **betik**.<br /><br /> -   **Yalnızca yerel** yönetilmeyen C++ kodudur.<br />-   **Yalnızca yönetilen** ortak dil çalışma zamanı altında (yönetilen kod) çalışan bir kod içindir.<br />-   **Karma** hem yönetilen hem de yönetilmeyen kod için hata ayıklayıcıları çağırır.<br />-   **Otomatik** derleyici ve EXE bilgileri temelinde hata ayıklayıcı türü belirler.<br />-   **Komut dosyası** betikler için hata ayıklayıcı çağırır.<br />-   **Yalnızca GPU** DirectX görüntüleyiciye veya GPU cihaz üzerinde çalışan C++ AMP kod içindir. Bkz: [GPU kodunda hata ayıklama](../debugger/debugging-gpu-code.md).|  
|**Ortam** (yerel Windows hata ayıklayıcı ve uzak Windows hata ayıklayıcı)|Hata ayıklama yaptığınız program için ortam değişkenlerini belirtir. Standart ortam değişkeni söz dizimini kullanın (örneğin, `PATH="%SystemRoot%\..."`). Bu değişkenler sistem ortam geçersiz kılabilir veya bağlı olarak sistem ortamı birleştirilmiş **birleştirme ortamı** ayarı. Ayarları sütununda tıklattığınızda, bir "Düzenle …" görüntülenir. Ortam değişkenleri düzenlemek için bu bağlantıyı tıklatın.|  
|**Ortam birleştirme** (yerel Windows hata ayıklayıcı)|Değişkenleri, olup olmadığını belirler belirtilen **ortam** kutusu, işletim sistemi tarafından tanımlanan ortam ile birleştirilir. Evet varsayılan ayardır.|  
|**SQL hata ayıklama** (tüm ancak MPI küme hata ayıklayıcı)|SQL yordamlardan birini hata ayıklamasını etkinleştirir, [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] uygulama. Varsayılan ayar Hayır.|  
|**Hızlandırıcı türü hata ayıklama** (GPU yalnızca hata ayıklama)|Hata ayıklama için kullanılacak GPU aygıtı belirtir. Uyumlu GPU aygıtları için aygıt sürücüleri yükleme ek seçenekleri ekler. Varsayılan ayardır "GPU - yazılım öykünücüsü."|  
|**GPU varsayılan kesme noktası davranışı** (GPU yalnızca hata ayıklama)|Kesme noktası olay SIMD tüneli içindeki her iş parçacığı için oluşturup oluşturmadığını belirler. Kesme noktası olay tüneli başına yalnızca bir kez yükseltmek için varsayılan ayardır.|  
|**Amp varsayılan Hızlandırıcı**|GPU kodunda hata ayıklama sırasında varsayılan AMP Hızlandırıcı belirtir. Seçin **TÜNELİ Yazılım hızlandırıcı** donanım ya da bir sürücü kodunuzu yerine bir soruna neden olursa araştırmak için.|  
|**Dağıtım dizini** (uzak Windows hata ayıklayıcı)|Proje çıktı başlatmak için kopyalanan önceki burada olacaktır uzak bilgisayarda yolunu belirtir. Yol, uzak bilgisayardaki bir ağ paylaşımına veya bir uzak bilgisayarda bir klasör yolu olabilir. Varsayılan ayar boş proje çıktısı bir ağ paylaşımına kopyalanmaz anlamına gelir. Dosyaları dağıtımını etkinleştirmek için de seçmelisiniz **dağıtma** Configuration Manager iletişim kutusundaki onay kutusu. Daha fazla bilgi için bkz: [nasıl yapılır: yapılandırmaları oluşturma ve düzenleme](../ide/how-to-create-and-edit-configurations.md).|  
|**Dağıtmak için ek dosyalar** (uzak Windows hata ayıklayıcı)|Dağıtım dizin özelliği ayarlarsanız, dağıtım dizinine kopyalamak için ek dosyalar noktalı virgülle ayrılmış listesini budur. Varsayılan ayar boş, hiçbir ek dosyalar dağıtım dizinine kopyalanır anlamına gelir. Dosyaları dağıtımını etkinleştirmek için de seçmelisiniz **dağıtma** Configuration Manager iletişim kutusundaki onay kutusu. Daha fazla bilgi için bkz: [nasıl yapılır: yapılandırmaları oluşturma ve düzenleme](../ide/how-to-create-and-edit-configurations.md).|  
|**Visual C++ hata ayıklama çalışma zamanı kitaplıkları dağıtmak** (uzak Windows hata ayıklayıcı)|Dağıtım dizini özellik ayarlanırsa, bu ağ paylaşımına geçerli platform için Visual C++ hata ayıklama çalışma zamanı kitaplıkları kopyalanıp kopyalanmayacağını belirtir. Evet varsayılan ayardır.|  
  
## <a name="cc-folder-general-category"></a>C/C++ klasörü (genel kategori)  
  
|Ayar|Açıklama|  
|-------------|-----------------|  
|**Hata ayıklama bilgileri biçimi** ([/Z7, /Zd, Zi, /zı](/cpp/build/reference/z7-zi-zi-debug-information-format))|Proje için oluşturulacak hata ayıklama bilgi türünü belirtir.<br /><br /> Varsayılan seçenek (/ZI) Düzenle ve devam et uyumlu bir biçimde program veritabanı (PDB) oluşturur. Daha fazla bilgi için bkz: [/Z7, /Zd, / zi, /zı (hata ayıklama bilgileri biçimi)](/cpp/build/reference/z7-zi-zi-debug-information-format).|  
  
## <a name="cc-folder-optimization-category"></a>C/C++ klasörü (en iyi duruma getirme kategori)  
  
|Ayar|Açıklama|  
|-------------|-----------------|  
|**En iyi duruma getirme**|Derleyici bu üretir kodu İyileştir olup olmadığını belirtir. En iyi duruma getirme yürütülen kod değiştirir. İyileştirilmiş kod artık kaynak kodu eşleşir. Bu nedenle, hata ayıklama zordur.<br /><br /> Varsayılan seçenek (**devre dışı (/ 0d**) en iyi duruma getirme gizler. Gizlenen iyileştirme ile geliştirin ve kodunuzu üretim sürümünü oluşturduğunuzda açın.|  
  
## <a name="linker-folder-debugging-category"></a>Bağlayıcı klasörü (hata ayıklama kategori)  
  
|Ayar|Açıklama|  
|-------------|-----------------|  
|**Hata ayıklama bilgileri üret** ([/DEBUG](/cpp/build/reference/debug-generate-debug-info))|Bağlayıcı /Z7, /Zd, Zi veya/zi tarafından belirtilen biçimde olacaktır hata ayıklama bilgileri içerecek şekilde söyler.|  
|**Program veritabanı dosyası oluşturma** ([/PDB:name](/cpp/build/reference/pdb-use-program-database))|PDB dosyası adını bu kutuda belirtin. Hata ayıklama bilgileri biçimi için ZI veya/zi seçmeniz gerekir.|  
|**Özel simgeleri** ([/PDBSTRIPPED:filename](/cpp/build/reference/pdbstripped-strip-private-symbols))|Özel sembolleri PDB dosyasında dahil etmek istemiyorsanız, bu kutuda PDB dosya adını belirtin. / Debug, /Z7, /Zd gibi bir PDB dosyası oluşturma seçenekleri program yansımanıza derleyici veya bağlayıcı yapılandırdığınızda bu seçenek ikinci bir program veritabanı (PDB) dosyası oluşturur. Veya/zi. Bu ikinci PDB dosyası, sevk müşterilerinize istemezsiniz simgeleri atlar. Daha fazla bilgi için bkz: [/PDBSTRIPPED (özel simgeleri)](/cpp/build/reference/pdbstripped-strip-private-symbols).|  
|**Eşlem dosyası oluşturma** ([/MAP](/cpp/build/reference/map-generate-mapfile))|Bağlama sırasında bir harita dosyası oluşturmak için bağlayıcıya bildirir. Varsayılan ayar Hayır. Daha fazla bilgi için bkz: [/Map (eşlem dosyası oluştur)](/cpp/build/reference/map-generate-mapfile).|  
|**Dosya adı eşleme** ([/MAP:](/cpp/build/reference/map-generate-mapfile)*adı*)|Harita dosyası oluşturmak isterseniz, bu kutuda eşleme dosyası belirtebilirsiniz. Daha fazla bilgi için bkz: [/Map (eşlem dosyası oluştur)](/cpp/build/reference/map-generate-mapfile).|  
|**Dışarı aktarma eşleme** ([/MAPINFO:EXPORTS](/cpp/build/reference/mapinfo-include-information-in-mapfile))|Eşleme dosyasında dışarı aktarılan işlevler içerir. Varsayılan ayar Hayır. Daha fazla bilgi için bkz: [/MAPINFO (eşlem dosyası bilgileri dahil)](/cpp/build/reference/mapinfo-include-information-in-mapfile).|  
|**Debuggable derleme** ([/ASSEMBLYDEBUG](/cpp/build/reference/mapinfo-include-information-in-mapfile))|Bağlayıcı ayarlarını belirtir. /ASSEMBLYDEBUG seçeneği. Olası değerler aşağıdaki gibidir:<br /><br /> -   **Gösterilen debuggable özniteliği yok**.<br />-   **Çalışma zamanı izleme ve devre dışı bırakma iyileştirmeleri (/ ASSEMBLYDEBUG)**. Varsayılan ayar budur,<br />-   **Çalışma zamanı izleme ve etkinleştir optimizations(/ASSEMBLYDEBUG:DISABLE)**.<br />-   **\<üst ya da proje varsayılan adlardan devral >**.<br />-Daha fazla bilgi için [/ASSEMBLYDEBUG (DebuggableAttribute ekleme)](/cpp/build/reference/assemblydebug-add-debuggableattribute).|  
  
 Program aracılığıyla Microsoft.VisualStudio.VCProjectEngine.VCDebugSettings arabirimini kullanarak yapılandırma özelliklerini klasöründe (hata ayıklama kategori) bu ayarları değiştirebilirsiniz. Daha fazla bilgi için bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCDebugSettings>.

## <a name="other-project-settings"></a>Diğer proje ayarları

Statik kitaplıklar ve DLL'ler gibi proje türleri hata ayıklamak için Visual Studio projenizi doğru dosyaları bulamıyor olması gerekir. Kaynak kodu kullanılabilir olduğunda, ayrı projeler olarak statik kitaplıklar ve DLL'ler (Bu kolay hata ayıklama yapmaz) çözüme ekleyebilirsiniz. Bu proje türleri oluşturma konusunda daha fazla bilgi için bkz: [oluşturma ve dinamik bağlantı kitaplığı (DLL) kullanarak](/cpp/build/walkthrough-creating-and-using-a-dynamic-link-library-cpp) ve [kullanarak bir statik kitaplık oluşturma](/cpp/windows/walkthrough-creating-and-using-a-static-library-cpp). Kullanılabilir kaynak kodu ile yeni bir Visual Studio projesi seçerek oluşturabilirsiniz **Dosya > Yeni > Proje ilk var olan kodu**.

Projenize dış DLL'leri hata ayıklamak için bkz: [hata ayıklama DLL projeleri](../debugger/debugging-dll-projects.md#vxtskdebuggingdllprojectsexternal). Gerekirse kendi DLL projesinde hata ayıklama ancak yok çağıran uygulama projesi erişimi görmek [DLL projesinde hata ayıklamak nasıl](../debugger/how-to-debug-from-a-dll-project.md).
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)   
 [Hata ayıklayıcı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)   
 [Visual C++ proje oluşturma ve yönetme](/cpp/ide/creating-and-managing-visual-cpp-projects)   
 [/ ASSEMBLYDEBUG (DebuggableAttribute ekleme)](/cpp/build/reference/assemblydebug-add-debuggableattribute)   
 [Genel Derleme Komutları ve Özellikler Makroları](/cpp/ide/common-macros-for-build-commands-and-properties)