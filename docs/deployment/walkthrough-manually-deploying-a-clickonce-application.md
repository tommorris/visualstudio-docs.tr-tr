---
title: 'İzlenecek yol: Bir ClickOnce uygulamasını el ile dağıtma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Mage.exe, manual ClickOnce deployments
- MageUI.exe, manual ClickOnce deployments
- deploying applications [ClickOnce], manual ClickOnce deployments
- ClickOnce deployment, manually
- ClickOnce deployment, SDK tools
- manual ClickOnce deployments
- manifests [ClickOnce]
ms.assetid: ccee6551-a1b9-4ca2-8845-9c1cf4ac2560
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 001aa8f3436e1594b198a81779c77258ca829a21
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-manually-deploying-a-clickonce-application"></a>İzlenecek yol: ClickOnce Uygulamasını El ile Dağıtma
Dağıtmak için Visual Studio kullanamıyorsanız, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama veya gelişmiş dağıtım özelliklerini kullanmanız gereken güvenilir uygulama dağıtımı gibi oluşturmak için Mage.exe komut satırı aracını kullanmanız gerekir, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bildirimleri. Bu kılavuzda nasıl oluşturulacağını açıklar bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] komut satırı sürümünü (Mage.exe) veya grafik sürümünü (MageUI.exe) bildirim oluşturma ve düzenleme aracı kullanarak dağıtım.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzda, bazı Önkoşullar ve bir dağıtım oluşturmadan önce seçmeniz gerekiyor seçenekleri vardır.  
  
-   Mage.exe ve MageUI.exe yükleyin.  
  
     Mage.exe ve MageUI.exe parçası olan [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. Ya da olmalıdır [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] yüklü sürümünü veya [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] Visual Studio'ya eklenmiş. Daha fazla bilgi için bkz: [Windows SDK](http://go.microsoft.com/fwlink/?LinkId=158044) konusuna bakın.  
  
-   Dağıtmak üzere bir uygulama sağlar.  
  
     Bu kılavuz, dağıtım için hazır olan bir Windows uygulaması olduğunu varsayar. Bu uygulama AppToDeploy olarak anılacaktır.  
  
-   Dağıtımın nasıl dağıtılacağı belirler.  
  
     Dağıtım seçenekleri şunları içerir: Web, dosya paylaşımı veya CD. Daha fazla bilgi için bkz: [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md).  
  
-   Uygulamanın yükseltilmiş bir güven düzeyini ihtiyacı olup olmadığını belirler.  
  
     Uygulamanız tam güven gerektiriyorsa — Örneğin, kullanıcının sisteme erişim tam — kullanabileceğiniz `-TrustLevel` bunu ayarlamak için Mage.exe seçeneği. Uygulamanız için özel bir izni tanımlamak istiyorsanız, Internet veya intranet izin bölümünü başka bir bildirimden kopyalayın, gereksinimlerinize uyacak şekilde değiştirin ve bir metin düzenleyicisi veya MageUI.exe kullanarak uygulama bildirimi ekleyin. Daha fazla bilgi için bkz: [güvenilir uygulama dağıtımına genel bakış](../deployment/trusted-application-deployment-overview.md).  
  
-   Authenticode sertifikası edinin.  
  
     Authenticode sertifikası ile dağıtımınızı imzalamanız gerekir. Visual Studio, MageUI.exe veya MakeCert.exe ve Pvk2Pfx.exe araçlarını kullanarak bir test sertifikası oluşturabilir veya bir sertifika yetkilisi (CA) bir sertifika edinebilirsiniz. Güvenilir uygulama dağıtımı kullanmayı seçerseniz, tüm istemci bilgisayarlara sertifika tek seferlik bir yüklemesi gerçekleştirmeniz gerekir. Daha fazla bilgi için bkz: [güvenilir uygulama dağıtımına genel bakış](../deployment/trusted-application-deployment-overview.md).  
  
    > [!NOTE]
    >  Ayrıca bir sertifika yetkilisinden elde edebilirsiniz CNG sertifika dağıtımınıza oturum açabilir.  
  
-   Uygulama bildirimini UAC bilgilerle yok emin olun.  
  
     Uygulamanızı bir bildirimi, kullanıcı hesabı denetimi (UAC) bilgilerle gibi içerip içermediğini belirlemek gereken bir `<dependentAssembly>` öğesi. Bir uygulama bildirimi incelemek için Windows Sysinternals'dan kullanabilirsiniz [Sigcheck](http://go.microsoft.com/fwlink/?LinkId=158035) yardımcı programı.  
  
     Uygulamanızı bildirim UAC ayrıntılarla içeriyorsa, UAC bilgisi olmadan yeniden oluşturmalısınız. Bir C# projesi için Visual Studio Proje özelliklerini açın ve uygulama sekmesini seçin. İçinde **bildirim** aşağı açılan listesinden, **bildirim olmadan uygulama oluşturma**. Visual Studio'da bir Visual Basic proje için proje özelliklerini açın, uygulama sekmesini seçin ve tıklatın **görünümü UAC ayarları**. Açılan bildirim dosyasında tek içinde tüm öğeleri kaldırmak `<asmv1:assembly>` öğesi.  
  
-   Uygulamanın istemci bilgisayarda önkoşullar gerekli olup olmadığını belirler.  
  
     [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Visual Studio'dan dağıtılan uygulamaları dağıtımınız ile birlikte bir önkoşul önyükleyicisi (setup.exe) içerebilir. Bu kılavuz için gerekli iki bildirim oluşturur bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım. Kullanarak bir önkoşul önyükleyicisi oluşturabilirsiniz [GenerateBootstrapper görevi](../msbuild/generatebootstrapper-task.md).  
  
### <a name="to-deploy-an-application-with-the-mageexe-command-line-tool"></a>Mage.exe komut satırı aracını kullanarak bir uygulamayı dağıtmak için  
  
1.  Depolayacağınız bir dizin oluşturun, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım dosyaları.  
  
2.  Az önce oluşturduğunuz dağıtım dizininde bir sürüm alt dizini oluşturun. Uygulamayı ilk kez dağıtıyorsanız, sürüm alt ad **1.0.0.0**.  
  
    > [!NOTE]
    >  Dağıtımınızın sürümü, uygulamanızın sürümünden farklı olabilir.  
  
3.  Tüm uygulama dosyalarını, yürütülebilir dosyalar, derlemeleri, kaynakları ve veri dosyalarını içeren sürüm alt dizinine kopyalayın. Gerekirse, ek dosyaları içeren ek alt dizinleri oluşturabilirsiniz.  
  
4.  Açık [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] veya Visual Studio komut istemine ve sürüm alt dizinine geçin.  
  
5.  Mage.exe çağrısıyla uygulama bildirimi oluşturun. Aşağıdaki deyim Intel x86 işlemci üzerinde çalışmak üzere derlenmiş kod için bir uygulama bildirimi oluşturur.  
  
    ```  
    mage -New Application -Processor x86 -ToFile AppToDeploy.exe.manifest -name "My App" -Version 1.0.0.0 -FromDirectory .   
    ```  
  
    > [!NOTE]
    >  Nokta (.) eklediğinizden emin olun `-FromDirectory` geçerli dizin belirten seçeneği. Nokta eklemezseniz uygulama dosyalarınızı yolunu belirtmeniz gerekir.  
  
6.  Uygulama bildirimini Authenticode sertifikanızla imzalayın. Değiştir *mycert.pfx'i* ile sertifika dosyanızın yolu. Değiştir *parola* sertifika dosyanızın parolayla.  
  
    ```  
    mage -Sign AppToDeploy.exe.manifest -CertFile mycert.pfx -Password passwd  
    ```  
  
     CNG sertifikayla uygulama bildiriminizi imzalamak için aşağıdakileri kullanın. Değiştir *cngCert.pfx* ile sertifika dosyanızın yolu.  
  
    ```  
    mage -Sign AppToDeploy.exe.manifest -CertFile cngCert.pfx  
    ```  
  
7.  Dağıtım dizini kök dizinine değiştirin.  
  
8.  Mage.exe çağrısıyla dağıtım bildirimi oluşturur. Varsayılan olarak, Mage.exe işaretler, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtımı yüklenmiş bir uygulama, BT'nin hem çevrimiçi çalıştırabilmeniz için ve çevrimdışı olarak. Kullanıcının çevrimiçi olduğunda uygulama kullanılabilir yapmak için `-Install` değerini seçeneğiyle `false`. Varsayılan kullanıyorsanız ve kullanıcılar, uygulamanızın yükler, bir Web sitesi veya dosya paylaşımından emin olun değerini `-ProviderUrl` Web sunucusunun veya paylaşım uygulamasının konumunu seçeneği noktalarına bildirimi.  
  
    ```  
    mage -New Deployment -Processor x86 -Install true -Publisher "My Co." -ProviderUrl "\\myServer\myShare\AppToDeploy.application" -AppManifest 1.0.0.0\AppToDeploy.exe.manifest -ToFile AppToDeploy.application  
    ```  
  
9. Dağıtım bildirimini Authenticode veya CNG sertifikanızla imzalayın.  
  
    ```  
    mage -Sign AppToDeploy.application -CertFile mycert.pfx -Password passwd  
    ```  
  
     veya  
  
    ```  
    mage -Sign AppToDeploy.exe.manifest -CertFile cngCert.pfx  
    ```  
  
10. Dağıtım hedefi veya medya tüm dosyaları dağıtım dizininde kopyalayın. Bu bir Web sitesi veya FTP sitesi, bir dosya paylaşımı veya bir CD-ROM ya da bir klasör olabilir.  
  
11. Kullanıcılarınızın URL, UNC veya uygulamanızı yüklemek için gereken fiziksel ortam sağlar. Bir URL veya UNC sağlarsanız, kullanıcılarınız için dağıtım bildirimi tam yolunu vermeniz gerekir. Örneğin, AppToDeploy dağıtılırsa http://webserver01/ AppToDeploy dizininde tam URL yolu olacaktır http://webserver01/AppToDeploy/AppToDeploy.application.  
  
### <a name="to-deploy-an-application-with-the-mageuiexe-graphical-tool"></a>MageUI.exe grafik Aracı'yla bir uygulamayı dağıtmak için  
  
1.  Depolayacağınız bir dizin oluşturun, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım dosyaları.  
  
2.  Az önce oluşturduğunuz dağıtım dizininde bir sürüm alt dizini oluşturun. Uygulamayı ilk kez dağıtıyorsanız, sürüm alt ad **1.0.0.0**.  
  
    > [!NOTE]
    >  Dağıtımınızın sürümünden büyük olasılıkla, uygulamanızın sürümünden farklıdır.  
  
3.  Tüm uygulama dosyalarını, yürütülebilir dosyalar, derlemeleri, kaynakları ve veri dosyalarını içeren sürüm alt dizinine kopyalayın. Gerekirse, ek dosyaları içeren ek alt dizinleri oluşturabilirsiniz.  
  
4.  MageUI.exe grafik aracını başlatın.  
  
    ```  
    MageUI.exe  
    ```  
  
5.  Seçerek yeni bir uygulama bildirimi oluşturmak **dosya**, **yeni**, **uygulama bildirimi** menüsünde.  
  
6.  Varsayılan **adı** sekmesinde, bu dağıtımın adını ve sürüm numarasını yazın. Ayrıca belirtin **İşlemci** , uygulamanız için x86 gibi yerleşik olarak bulunur.  
  
7.  Seçin **dosyaları** sekmesinde ve üç nokta işaretine (**...** ) düğmesine **uygulama dizini** metin kutusu. Bir klasöre Gözat iletişim kutusu görüntülenir.  
  
8.  Uygulama dosyalarını içeren sürüm alt dizini seçin ve ardından **Tamam**.  
  
9. Internet Information Services (IIS) dağıtacaksanız işaretleyin **doldurma eklediğinizde .deploy uzantısı yok herhangi bir dosyaya** onay kutusu.  
  
10. Tıklatın **Populate** tüm uygulama dosyalarını dosya listesine eklemek için düğmeyi. Uygulamanız birden fazla yürütülebilir dosya içeriyorsa, bu dağıtım için başlangıç uygulaması olarak ana yürütülebilir dosyayı seçerek işaretleyin **giriş noktası** gelen **dosya türü** aşağı açılan liste. (Uygulamanızın tek bir yürütülebilir dosya içeriyorsa, MageUI.exe bunu sizin için işaretler.)  
  
11. Seçin **gerekli izinler** sekmesinde ve onaylanacak uygulamanız gereken güven düzeyini seçin. Varsayılan değer **FullTrust**, çoğu uygulama için uygun olacak.  
  
12. Seçin **dosya**, **Kaydet** menüsünde. Uygulama bildiriminizi imzalamak için imzalama Seçenekleri iletişim kutusu görüntülenir.  
  
13. Dosya sisteminizi dosya olarak depolanan bir sertifika varsa, **sertifika dosyası işaretiyle** seçeneği ve üç nokta kullanarak dosya sisteminden sertifikayı seçin (**...** ) düğmesi. Sertifika parolanızı yazın.  
  
     -veya-  
  
     Sertifikanızı sertifika deposunda bilgisayarınızdan erişilebilir kaldığı seçin **depolanan bir sertifika ile oturum** seçeneği ve verilen listeden sertifikayı seçin.  
  
14. Tıklatın **Tamam** uygulama bildiriminizi imzalamak için. Farklı Kaydet iletişim kutusu görüntülenir.  
  
15. Farklı Kaydet iletişim kutusunda sürüm dizinini belirtin ve ardından **kaydetmek**.  
  
16. Seçin **dosya**, **yeni**, **dağıtım bildirimi** Dağıtım bildiriminizi oluşturmak için menüsünden.  
  
17. Üzerinde **adı** sekmesinde, bu dağıtım için bir ad ve sürüm numarası belirtin (**1.0.0.0** Bu örnekte). Ayrıca belirtin **İşlemci** , uygulamanız için x86 gibi yerleşik olarak bulunur.  
  
18. Seçin **açıklama** sekmesini tıklatın ve değerlerini belirtin **yayımcı** ve **ürün *** t**. (**Ürün** uygulamanızı çevrimdışı kullanım için bir istemci bilgisayara yüklendiğinde, Windows Başlat menüsündeki uygulamanıza verilen addır.)  
  
19. Seçin **dağıtım seçenekleri** sekmesi hem de **Başlat konumu** metin kutusunda, Web sunucusu veya paylaşım üzerindeki uygulama bildiriminin konumunu belirtin. Örneğin, \\\myServer\myShare\AppToDeploy.application.  
  
20. Önceki adımda .deploy uzantısı eklediyseniz, ayrıca seçin **.deploy dosya adı uzantısını kullanacak** burada.  
  
21. Seçin **Güncelleştirme Seçenekleri** sekmesini tıklatın ve güncelleştirmek için bu uygulamayı sıklığını belirtin. Uygulamanız kullanıyorsa <xref:System.Deployment.Application.UpdateCheckInfo> kendisini güncelleştirmeleri denetlemek için temizleyin **bu uygulama güncelleştirmeleri denetleyeceğini** onay kutusu.  
  
22. Seçin **uygulama başvurusu** sekmesini ve sonra **seçin bildirim** düğmesi. Açık bir iletişim kutusu görüntülenir.  
  
23. Daha önce oluşturduğunuz uygulama bildirimini seçin ve ardından **açık**.  
  
24. Seçin **dosya**, **Kaydet** menüsünde. Uygulama bildirimini imzalamak için imzalama Seçenekleri iletişim kutusu görüntülenir.  
  
25. Dosya sisteminizi dosya olarak depolanan bir sertifika varsa, **sertifika dosyası işaretiyle** seçeneği ve üç nokta kullanarak dosya sisteminden sertifikayı seçin (**...** ) düğmesi. Sertifika parolanızı yazın.  
  
     -veya-  
  
     Sertifikanızı sertifika deposunda bilgisayarınızdan erişilebilir kaldığı seçin **depolanan bir sertifika ile oturum** seçeneği ve verilen listeden sertifikayı seçin.  
  
26. Tıklatın **Tamam** Dağıtım bildiriminizi imzalamak için. Farklı Kaydet iletişim kutusu görüntülenir.  
  
27. İçinde **Kaydet** iletişim kutusu, dağıtım ve ardından kökünde bir dizin Yukarı Taşı **kaydetmek**.  
  
28. Dağıtım hedefi veya medya tüm dosyaları dağıtım dizininde kopyalayın. Bu bir Web sitesi veya FTP sitesi, bir dosya paylaşımı veya bir CD-ROM ya da bir klasör olabilir.  
  
29. Kullanıcılarınızın URL, UNC veya uygulamanızı yüklemek için gereken fiziksel ortam sağlar. Bir URL veya UNC sağlarsanız, dağıtım bildirimi tam yolu, kullanıcılarınızın vermeniz gerekir. Örneğin, AppToDeploy dağıtılırsa http://webserver01/ AppToDeploy dizininde tam URL yolu olacaktır http://webserver01/AppToDeploy/AppToDeploy.application.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Uygulamanın yeni bir sürümünü dağıtmak gerektiğinde, sonra yeni sürümü adlı yeni bir dizin oluşturma — Örneğin, 1.0.0.1 yeni uygulama dosyaları kopyalama yeni dizine. Ardından, oluşturmak ve yeni bir uygulama bildirimi oturum ve güncelleştirme ve uygulama bildirimini imzalamak için önceki adımları izlemeniz gerekir. Mage.exe içinde aynı yüksek bir sürüme belirtilmesi konusunda dikkatli olun `-New` ve `-Update` çağrıları, olarak [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] yalnızca daha sonraki sürümler en soldaki tamsayı en önemli güncelleştirir. MageUI.exe kullandıysanız, dağıtım bildirimi, açarak seçerek güncelleştirebilirsiniz **uygulama başvurusu** sekmesini tıklatarak, **seçin bildirim** düğmesine tıklayın ve ardından güncelleştirilmiş seçme Uygulama bildirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Mage.exe (bildirim üretme ve düzenleme aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (bildirim üretme ve düzenleme aracı, grafik istemci)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)   
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [ClickOnce dağıtım bildirimi](../deployment/clickonce-deployment-manifest.md)   
 [ClickOnce Uygulama Bildirimi](../deployment/clickonce-application-manifest.md)