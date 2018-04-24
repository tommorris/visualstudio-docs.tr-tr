---
title: Komut satırından ClickOnce uygulamalarını derleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, from command line
- publishing
- publishing, ClickOnce
ms.assetid: d9bc6212-c584-4f72-88c9-9a4b998c555e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4488f32b135d766f494bc94946fbf77d42eb1e95
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="building-clickonce-applications-from-the-command-line"></a>Komut Satırından ClickOnce Uygulamalarını Derleme
İçinde [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], tümleşik geliştirme ortamı (IDE) oluşturulmamış olsa bile, komut satırından projeleri oluşturabilirsiniz. İle oluşturulmuş bir projeyi yeniden aslında, [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yalnızca sahip başka bir bilgisayarda [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] yüklü. Bu, otomatik bir işlem kullanarak bir yapı oluşturmanızı sağlar, örneğin, merkezi bir yapı içinde Laboratuvar Gelişmiş ya da kullanarak teknikleri projeyi oluşturmayı kapsamı dışında.  
  
## <a name="using-msbuild-to-reproduce-clickonce-application-deployments"></a>ClickOnce Uygulama dağıtımlarını yeniden oluşturmak için MSBuild kullanma  
 Komut satırında msbuild/target: publish çağırdığınızda, projeyi derlemek ve oluşturmak için MSBuild sistem söyleyen bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Yayımla klasöründeki uygulama. Bu seçmeye eşdeğerdir **Yayımla** IDE'de komutu.  
  
 Bu komut, Visual Studio komut istemi ortamı yolunda açıktır msbuild.exe yürütür.  
  
 "Hedef" bir MSBuild komutu işlemek nasıl göstergesidir. Anahtar hedefler "yapı" hedef ve "Yayımla" hedef ' dir. Yapı hedefi derleme seçme eşdeğerdir IDE komut (veya F5'e basarak). Yalnızca projenizi oluşturmak istiyorsanız, bunu, yazarak elde edebilirsiniz `msbuild`. Tarafından oluşturulan tüm projeleri için varsayılan hedef yapı hedefi olduğu için bu komut çalışır [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]. Başka bir deyişle, açıkça yapı hedefi belirtmeniz gerekmez. Bu nedenle, yazarak `msbuild` yazarak olarak aynı işlem `msbuild /target:build`.  
  
 `/target:publish` Komutu yayımlama hedefi MSBuild'e bildirir. Yayımlama hedefi yapı hedefine bağlıdır. Başka bir deyişle, yayımlama işlemi oluşturma işlemi bir üst kümesidir. Örneğin, Visual Basic veya C# kaynak dosyalarınız birine bir değişiklik yaptıysanız, karşılık gelen derleme Yayımla işlemi tarafından otomatik olarak yeniden yapılandırılacaktır.  
  
 Tam oluşturma hakkında bilgi için [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] oluşturmak için Mage.exe komut satırı aracını kullanarak dağıtımı, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bildirimi için bkz: [izlenecek yol: bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
## <a name="creating-and-building-a-basic-clickonce-application-using-msbuild"></a>Oluşturma ve MSBuild kullanarak temel ClickOnce uygulaması oluşturma  
  
#### <a name="to-create-and-publish-a-clickonce-project"></a>Oluşturma ve bir ClickOnce projesi yayımlama  
  
1.  Tıklatın **yeni proje** gelen **dosya** menüsü. **Yeni proje** iletişim kutusu görüntülenir.  
  
2.  Seçin **Windows uygulaması** ve adlandırın `CmdLineDemo`.  
  
3.  Gelen **yapı** menüsünde tıklatın **Yayımla** komutu.  
  
     Projeyi oluşturmak için düzgün yapılandırıldığından bu adım sağlar bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama dağıtımı.  
  
     Yayımlama Sihirbazı görünür.  
  
4.  Yayımlama Sihirbazı'nı tıklatın **son**.  
  
     Visual Studio oluşturur ve Publish.htm adlı varsayılan Web sayfası görüntülenir.  
  
5.  Projeyi kaydedin ve, depolandığı klasör konumunu not edin.  
  
 Yukarıdaki adımları oluşturma bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ilk kez yayımlanan projesi. Artık derleme IDE dışında yeniden oluşturabilirsiniz.  
  
#### <a name="to-reproduce-the-build-from-the-command-line"></a>Komut satırından derleme yeniden oluşturmak için  
  
1.  Çıkış [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)].  
  
2.  Windows **Başlat** menüsünde tıklatın **tüm programlar**, ardından **Microsoft Visual Studio**, ardından **Visual Studio Araçları**, sonra **Visual Studio komut istemi**. Bu, geçerli kullanıcının kök klasöründe bir komut istemi açın.  
  
3.  İçinde **Visual Studio komut istemi**, geçerli dizin yalnızca yerleşik yukarıda proje konumunu değiştirin. Örneğin, `chdir My Documents\Visual Studio\Projects\CmdLineDemo`.  
  
4.  Üretilen var olan dosyaları kaldırmak için "oluşturmak ve yayımlamak için bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] projesi" türü `rmdir /s publish`.  
  
     Bu adım isteğe bağlıdır, ancak yeni dosyalar tüm komut satırı derleme tarafından üretilmiş olan sağlar.  
  
5.  Türü `msbuild /target:publish`.  
  
 Yukarıdaki adımları tam üretecektir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] projenizin P adlı bir alt uygulama dağıtımı**Yayımla**. CmdLineDemo.Application [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım bildirimi. CmdLineDemo_1.0.0.0 klasörü CmdLineDemo.exe dosyaları CmdLineDemo.exe.manifest ve dosyalarını içeren [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimi. Setup.exe olduğundan, varsayılan olarak yüklemek için yapılandırılmış önyükleyici [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. DotNetFX klasörü için yeniden dağıtılabilir öğeleri içeren [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Web üzerinden veya UNC veya CD/DVD aracılığıyla uygulamanızı dağıtmak için gereken dosya kümesinin tamamını budur.  
  
## <a name="publishing-properties"></a>Yayımlama özellikleri  
 Aşağıdaki özellikleri Yukarıdaki yordamlarda uygulama yayımladığınızda, Yayımlama Sihirbazı tarafından proje dosyanıza eklenir. Bu özellikler doğrudan etkilemek nasıl [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama oluşturulur.  
  
 CmdLineDemo.vbproj / CmdLineDemo.csproj içinde:  
  
```  
<AssemblyOriginatorKeyFile>WindowsApplication3.snk</AssemblyOriginatorKeyFile>  
<GenerateManifests>true</GenerateManifests>  
<TargetZone>LocalIntranet</TargetZone>  
<PublisherName>Microsoft</PublisherName>  
<ProductName>CmdLineDemo</ProductName>  
<PublishUrl>http://localhost/CmdLineDemo</PublishUrl>  
<Install>true</Install>  
<ApplicationVersion>1.0.0.*</ApplicationVersion>  
<ApplicationRevision>1</ApplicationRevision>  
<UpdateEnabled>true</UpdateEnabled>  
<UpdateRequired>false</UpdateRequired>  
<UpdateMode>Foreground</UpdateMode>  
<UpdateInterval>7</UpdateInterval>  
<UpdateIntervalUnits>Days</UpdateIntervalUnits>  
<UpdateUrlEnabled>false</UpdateUrlEnabled>  
<IsWebBootstrapper>true</IsWebBootstrapper>  
<BootstrapperEnabled>true</BootstrapperEnabled>  
```  
  
 Proje dosyası değiştirmeden komut satırında bu özelliklerden herhangi birini geçersiz kılabilirsiniz. Örneğin, aşağıdaki oluşturacaksınız [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] önyükleyici olmadan uygulama dağıtımı:  
  
```  
msbuild /target:publish /property:BootstrapperEnabled=false  
```  
  
 Yayımlama özellikleri denetlenir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] gelen **Yayımla**, **güvenlik**, ve **imzalama** özellik sayfalarından **Proje Tasarımcısı** . Her Uygulama Tasarımcısı çeşitli özellik sayfalarında nasıl ayarlanır, bir göstergesi ile birlikte yayımlama özellikleri açıklaması aşağıdadır:  
  
-   `AssemblyOriginatorKeyFile` imzalamak için kullanılan anahtar dosyası belirler, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimleri. Bu aynı anahtar derlemeleriniz için güçlü bir ad atamak için de kullanılabilir. Bu özellik üzerinde ayarlanır **imzalama** sayfasında **Proje Tasarımcısı**.  
  
 Aşağıdaki özellikler ayarlanır **güvenlik** sayfa:  
  
-   **ClickOnce güvenlik ayarlarını etkinleştirme** belirler olup olmadığını [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bildirimleri oluşturulur. Bir proje başlangıçta oluşturulduğunda [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bildirim üretme varsayılan olarak kapalıdır. Sihirbazın bu bayrak, ilk kez yayımladığınızda üzerinde otomatik olarak açılır.  
  
-   **TargetZone** için güven düzeyini belirler, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimi. Olası değerler şunlardır: "Internet", "LocalIntranet" ve "Özel". Internet ve LocalIntranet için bir varsayılan izin neden olur, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimi. LocalIntranet varsayılan değerdir ve neredeyse tam güven anlamına gelir. Özel belirtir yalnızca temel app.manifest dosyasında açıkça belirtilen izinlerin içine yayınlaması olduğunu [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimi. App.manifest dosyası yalnızca güven bilgisi tanımlarını içeren kısmi bir bildirim dosyası değildir. Üzerinde izinleri yapılandırdığınızda projenize otomatik olarak eklenen gizli bir dosyadır **güvenlik** sayfası.  
  
 Aşağıdaki özellikler ayarlanır **Yayımla** sayfa:  
  
-   `PublishUrl` Burada uygulama IDE içinde yayımlanacak konumdur. İçine eklenen [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimi ne `InstallUrl` veya `UpdateUrl` özellik belirtilmiş.  
  
-   `ApplicationVersion` sürümünü belirtir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama. Bu dört basamaklı sürüm numarasıdır. Son rakam ise bir "*", ardından `ApplicationRevision` derleme zamanında bildirim içine eklenen değerin değiştirdi.  
  
-   `ApplicationRevision` Düzeltme belirtir. Bu, IDE içinde her yayımladığınızda artırır bir tamsayıdır. Bu otomatik olarak için artmaz dikkat edin, komut satırında gerçekleştirilen oluşturur.  
  
-   `Install` uygulamanın yüklü bir uygulama veya bir çalışma alanından Web uygulaması olup olmadığını belirler.  
  
-   `InstallUrl` (gösterilmez), kullanıcıların uygulamayı burada yükleyecek konumdur. Belirtilmişse, bu değer setup.exe önyükleyicisi içine `IsWebBootstrapper` özelliği etkin hale getirilir. Uygulama bildirim if eklenir `UpdateUrl` belirtilmedi.  
  
-   `SupportUrl` (gösterilmez) konumu bağlı olduğu **Program Ekle/Kaldır** yüklü bir uygulama için iletişim kutusu.  
  
 Aşağıdaki özellikleri ayarlayın **uygulama güncelleştirmeleri** iletişim kutusu, erişilen **Yayımla** sayfası.  
  
-   `UpdateEnabled` Uygulama Güncelleştirmeleri denetle olup olmadığını gösterir.  
  
-   `UpdateMode` ön plan güncelleştirmelerini ya da arka plan güncelleştirmeleri belirtir.  
  
-   `UpdateInterval` Uygulama güncelleştirmeleri ne sıklıkta denetleyeceğini belirtir.  
  
-   `UpdateIntervalUnits` belirtir olup olmadığını `UpdateInterval` saat, gün veya hafta birimlerinde bir değerdir.  
  
-   `UpdateUrl` (gösterilmez), uygulama güncelleştirmeleri alacağı konumdur. Belirtilmişse, bu değer uygulama bildirimine eklenir.  
  
-   Aşağıdaki özellikleri ayarlayın **Yayımla Seçenekleri** iletişim kutusu, erişilen **Yayımla** sayfası.  
  
-   `PublisherName` yükleme veya uygulamayı çalıştırdığınızda gösterilen istemde yayımcının adını belirtir. Yüklü bir uygulama olması durumunda da klasör adı belirtmeniz kullanıldığı **Başlat** menüsü.  
  
-   `ProductName` yükleme veya uygulamayı çalıştırdığınızda gösterilen istemde ürün adını belirtir. Yüklü bir uygulama olması durumunda da kısayol adını belirtmek için kullanıldığı **Başlat** menüsü.  
  
-   Aşağıdaki özellikleri ayarlayın **Önkoşullar** iletişim kutusu, erişilen **Yayımla** sayfası.  
  
-   `BootstrapperEnabled` setup.exe önyükleyici oluşturulup oluşturulmayacağını belirler.  
  
-   `IsWebBootstrapper` setup.exe önyükleyici Web üzerinden mi disk tabanlı modunda çalışıp çalışmadığını belirler.  
  
## <a name="installurl-supporturl-publishurl-and-updateurl"></a>InstallUrl, SupportUrl, PublishURL ve UpdateURL  
 Aşağıdaki tabloda ClickOnce dağıtım için dört URL seçeneklerini gösterir.  
  
|URL seçeneği|Açıklama|  
|----------------|-----------------|  
|`PublishURL`|ClickOnce uygulamanızı bir Web sitesi için yayımlama ise gereklidir.|  
|`InstallURL`|İsteğe bağlı. Bu URL seçeneğini yükleme sitesi farklı ise ayarlayın `PublishURL`. Örneğin, ayarlayabilir `PublishURL` bir FTP yolu ve kümesi `InstallURL` Web URL.|  
|`SupportURL`|İsteğe bağlı. Bu URL seçeneğini destek sitesi farklı ise ayarlayın `PublishURL`. Örneğin, ayarlayabilir `SupportURL` şirketinizin Müşteri Destek Web sitesi için.|  
|`UpdateURL`|İsteğe bağlı. Güncelleştirme konumu farklı ise, bu URL seçeneğini ayarlayın `InstallURL`. Örneğin, ayarlayabilir `PublishURL` bir FTP yolu ve kümesi `UpdateURL` Web URL.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.Build.Tasks.GenerateBootstrapper>   
 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest>   
 <xref:Microsoft.Build.Tasks.GenerateDeploymentManifest>   
 [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md)   
 [İzlenecek yol: ClickOnce Uygulamasını El ile Dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)