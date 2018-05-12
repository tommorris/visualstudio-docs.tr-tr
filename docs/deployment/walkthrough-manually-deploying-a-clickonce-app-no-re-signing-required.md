---
title: İzlenecek yol:, Yeniden imzalama gerektirmeyen ve marka bilgisini koruyan bir ClickOnce uygulamasını el ile dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- branding
- preserved branding information
- ClickOnce deployment, manually
- multiple ClickOnce deployment and branding
- ClickOnce deployment, SDK tools
- customer deployments
- manual ClickOnce deployments
- manifests [ClickOnce]
- ClickOnce applications, deployed by others
ms.assetid: c21822fb-d4ee-42e4-b72d-41ee9786efe5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0584aac376345bc508e5f2088decd45b8c64783b
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
---
# <a name="walkthrough-manually-deploying-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information"></a>İzlenecek yol: Yeniden İmzalama Gerektirmeyen ve Marka Bilgisini Koruyan bir ClickOnce Uygulamasını El ile Dağıtma
Oluştururken bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama ve yayımlamak için bir müşteri verin ve dağıtmak, müşteri geleneksel olarak dağıtım bildirimini güncelleştirmek ve yeniden imzalamak oluşturdu. Çoğu durumda tercih edilen yöntem, hala durumdayken, .NET Framework 3.5 oluşturmanızı sağlayan [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] müşteriler tarafından yeni bir dağıtım bildirimi yeniden oluşturmak zorunda kalmadan dağıtılabilir dağıtımları. Daha fazla bilgi için bkz: [dağıtma ClickOnce uygulamaları için sınama ve üretim sunucuları Resigning olmadan](../deployment/deploying-clickonce-applications-for-testing-and-production-without-resigning.md).  
  
 Oluştururken bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama ve yayımlamak için bir müşteri verin ve dağıtma, uygulama marka bilgilerinizi koruyabilir veya Müşteri'nin markalama kullanabilirsiniz. Örneğin, tek bir özel uygulama uygulamasıysa marka bilgilerinizi korumak isteyebilirsiniz. Uygulama her müşteri için yüksek oranda özelleştirilmiş, müşterinin markasını kullanmak isteyebilirsiniz. Dağıtmak üzere bir uygulama bir kuruluşa verdiğinizde .NET Framework 3.5, marka bilgilerinizi korumak için yayımcı bilgilerini ve güvenlik imzasını sağlar. Daha fazla bilgi için bkz: [ClickOnce uygulamaları oluşturma başkalarının dağıtma](../deployment/creating-clickonce-applications-for-others-to-deploy.md).  
  
> [!NOTE]
>  Bu kılavuzda, dağıtımları el ile komut satırı aracı Mage.exe veya MageUI.exe grafik aracını kullanarak oluşturun. Dağıtımlar hakkında daha fazla bilgi için bkz: [izlenecek yol: bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek adımları gerçekleştirmek için aşağıdakiler gerekir:  
  
-   Dağıtım için hazır olan bir Windows Forms uygulaması. Bu uygulama WindowsFormsApp1 olarak anılacaktır.  
  
-   Visual Studio veya Windows SDK.  
  
### <a name="to-deploy-a-clickonce-application-with-multiple-deployment-and-branding-support-using-mageexe"></a>Birden çok dağıtım Mage.exe kullanarak ve marka desteği ile bir ClickOnce uygulamasını dağıtmak için  
  
1.  Visual Studio komut istemi açın veya [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] komut istemi ve depolama dizinine değiştirin, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dosyaları.  
  
2.  Dağıtımınızın güncel sürümünden sonra adlı bir dizin oluşturun. Uygulamayı ilk kez dağıtıyorsanız, büyük olasılıkla seçecektir **1.0.0.0**.  
  
    > [!NOTE]
    >  Dağıtımınızın sürümünden uygulama dosyalarınızı sürümünden farklı olabilir.  
  
3.  Adlı bir alt oluşturma **bin** ve yürütülebilir dosyalar, derlemeleri, kaynakları ve veri dosyaları dahil olmak üzere tüm uygulama dosyalarınızı kopyalayın.  
  
4.  Mage.exe çağrısıyla uygulama bildirimi oluşturur.  
  
    ```  
    mage -New Application -ToFile 1.0.0.0\WindowsFormsApp1.exe.manifest -Name "Windows Forms App 1" -Version 1.0.0.0 -FromDirectory 1.0.0.0\bin -UseManifestForTrust true -Publisher "A. Datum Corporation"  
    ```  
  
5.  Uygulama bildirimini dijital sertifikanızla imzalayın.  
  
    ```  
    mage -Sign WindowsFormsApp1.exe.manifest -CertFile mycert.pfx  
    ```  
  
6.  Mage.exe çağrısıyla dağıtım bildirimi oluşturur. Varsayılan olarak, Mage.exe işaretler, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtımı yüklenmiş bir uygulama, BT'nin hem çevrimiçi çalıştırabilmeniz için ve çevrimdışı olarak. Kullanıcının çevrimiçi olduğunda uygulama kullanılabilir yapmak için `-i` bağımsız değişken değerini `f`. Bu uygulama birden çok dağıtım özelliğinden yararlanmak için dışarıda `-providerUrl` Mage.exe bağımsız değişkeni. (Dışlama .NET Framework sürüm 3.5, önce sürümlerinde `-providerUrl` için çevrimdışı bir uygulama bir hatayla sonuçlanır.)  
  
    ```  
    mage -New Deployment -ToFile WindowsFormsApp1.application -Name "Windows Forms App 1" -Version 1.0.0.0 -AppManifest 1.0.0.0\WindowsFormsApp1.manifest   
    ```  
  
7.  Dağıtım bildirimi oturum yok.  
  
8.  Kendi ağı üzerinde uygulamayı dağıtacak müşteriye tüm dosyaları sağlar.  
  
9. Bu noktada, müşteri dağıtım bildirimini kendi kendinden oluşturulmuş bir sertifika ile oturum açmanız gerekir. Örneğin, müşteri Adventure Works adlı bir şirket için çalışıyorsa, kendisinin MakeCert.exe aracını kullanarak otomatik olarak imzalanan bir sertifika oluşturabilirsiniz. Ardından, Mage.exe için geçirilen bir PFX dosyasına MakeCert.exe tarafından oluşturulan dosyaları birleştirmek için Pvk2pfx.exe aracını kullanın.  
  
    ```  
    makecert -r -pe -n "CN=Adventure Works" -sv MyCert.pvk MyCert.cer  
    pvk2pfx.exe -pvk MyCert.pvk -spc MyCert.cer -pfx MyCert.pfx  
    ```  
  
10. Müşteri, bu sertifikayı sonraki dağıtım bildirimini imzalamak için kullanır.  
  
    ```  
    mage -Sign WindowsFormsApp1.application -CertFile MyCert.pfx  
    ```  
  
11. Müşteri, kullanıcılar uygulamayı dağıtır.  
  
### <a name="to-deploy-a-clickonce-application-with-multiple-deployment-and-branding-support-using-mageuiexe"></a>Birden çok dağıtım ve marka desteği MageUI.exe kullanımı ile bir ClickOnce uygulamasını dağıtmak için  
  
1.  Visual Studio komut istemi açın veya [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] komut istemi ve depolama dizinine gidin, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dosyaları.  
  
2.  Adlı bir alt oluşturma **bin** ve yürütülebilir dosyalar, derlemeleri, kaynakları ve veri dosyaları dahil olmak üzere tüm uygulama dosyalarınızı kopyalayın.  
  
3.  Dağıtımınızın güncel sürümünden sonra adlı bir dizin oluşturun. Uygulamayı ilk kez dağıtıyorsanız, büyük olasılıkla seçecektir **1.0.0.0**.  
  
    > [!NOTE]
    >  Dağıtımınızın sürümünden uygulama dosyalarınızı sürümünden farklı olabilir.  
  
4.  Taşıma \\ **bin** 2. adımda oluşturduğunuz dizine dizin.  
  
5.  Grafik araç MageUI.exe başlatın.  
  
    ```  
    MageUI.exe  
    ```  
  
6.  Seçerek yeni bir uygulama bildirimi oluşturmak **dosya**, **yeni**, **uygulama bildirimi** menüsünde.  
  
7.  Varsayılan **adı** sekmesinde, bu dağıtımın adını ve sürüm numarasını girin. Ayrıca, için bir değer sağlamanız **yayımcı**, hangi kullanılacak Başlat menüsünde uygulamanın kısayol bağlantısı için klasör adı olarak dağıtıldığında.  
  
8.  Seçin **uygulama seçenekleri** sekmesinde **kullanım uygulama bildirimi güven bilgi**. Bu üçüncü taraf markayı etkinleştirecektir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama.  
  
9. Seçin **dosyaları** sekmesinde **Gözat** uygulama dizini metin kutusunun yanındaki düğmesi.  
  
10. 2. adımda oluşturduğunuz uygulama dosyalarını içeren dizini seçin ve tıklayın **Tamam** klasör seçimi iletişim kutusunda.  
  
11. Tıklatın **Populate** tüm uygulama dosyalarını dosya listesine eklemek için düğmeyi. Uygulamanız birden fazla yürütülebilir dosya içeriyorsa, bu dağıtım için başlangıç uygulaması olarak ana yürütülebilir dosyayı seçerek işaretleyin **giriş noktası** gelen **dosya türü** aşağı açılan liste. (Uygulamanızın yalnızca bir yürütülebilir dosya içeriyorsa, MageUI.exe bunu sizin için işaretler.)  
  
12. Seçin **gerekli izinler** sekmesinde ve onaylanacak uygulamanız gereken güven düzeyini seçin. Varsayılan değer **tam güven**, çoğu uygulama için uygun olacak.  
  
13. Seçin **dosya**, **kaydetmek** menüsünde ve uygulama bildirimini kaydedin. Kaydettiğinizde uygulama bildiriminizi imzalamak için istenir.  
  
14. Dosya sisteminizi dosya olarak depolanan bir sertifika varsa, **sertifika dosyası işarete** seçeneği ve üç nokta kullanarak dosya sisteminden sertifikayı seçin (**...** ) düğmesi.  
  
     -veya-  
  
     Bilgisayarınızdan erişilebilen bir sertifika deposunda sertifikanızı bıraktıysanız seçin **depolanan sertifika seçeneği ile oturum**ve verilen listeden sertifikayı seçin.  
  
15. Seçin **dosya**, **yeni**, **dağıtım bildirimi** menüsünde Dağıtım bildiriminizi oluşturmak ve ardından **adı** sekmesinde, kaynağı bir ad ve sürüm numarası (**1.0.0.0** Bu örnekte).  
  
16. Geçiş **güncelleştirme** sekmesini tıklatın ve bu uygulamayı güncelleştirmek için hangi sıklıkta güncelleştirileceğini belirtin. Uygulamanız kullanıyorsa [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım kendisi, güncelleştirmeleri denetlemek için API etiketli onay kutusunu temizleyin **bu uygulama güncelleştirmeleri denetleyeceğini**.  
  
17. Geçiş **uygulama başvurusu** sekmesi. Tüm değerleri bu sekmedeki tıklatarak önceden doldurmak **seçin bildirim** , düğmesi ve uygulama bildirimi seçerek önceki adımlarda oluşturduğunuz.  
  
18. Seçin **kaydetmek** ve dağıtım bildirimini diske kaydedin. Kaydettiğinizde uygulama bildiriminizi imzalamak için istenir. Tıklatın **iptal** bildirimi imzalamadan kaydetmek için.  
  
19. Tüm uygulama dosyalarını müşteriye sağlayın.  
  
20. Bu noktada, müşteri dağıtım bildirimini kendi kendinden oluşturulmuş bir sertifika ile oturum açmanız gerekir. Örneğin, müşteri Adventure Works adlı bir şirket için çalışıyorsa, kendisinin MakeCert.exe aracını kullanarak otomatik olarak imzalanan bir sertifika oluşturabilirsiniz. Ardından, MageUI.exe geçirilen bir PFX dosyasına MakeCert.exe tarafından oluşturulan dosyaları birleştirmek için Pvk2pfx.exe aracını kullanın.  
  
    ```  
    makecert -r -pe -n "CN=Adventure Works" -sv MyCert.pvk MyCert.cer  
    pvk2pfx.exe -pvk MyCert.pvk -spc MyCert.cer -pfx MyCert.pfx  
    ```  
  
21. Oluşturulan sertifika ile müşterinin artık dağıtım bildirimi MageUI.exe açma ve kaydetmeyi dağıtım bildirimi imzalar. İmzalama iletişim kutusu göründüğünde, müşteri seçer **sertifika dosyası işarete** seçeneği ve kendisine diskte kaydetti PFX dosyası seçer.  
  
22. Müşteri, kullanıcılar uygulamayı dağıtır.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Mage.exe (bildirim üretme ve düzenleme aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (bildirim üretme ve düzenleme aracı, grafik istemci)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)   
 [MakeCert](https://msdn.microsoft.com/library/windows/desktop/aa386968.aspx)