---
title: 'Nasıl yapılır: yeniden uygulama ve dağıtım bildirimlerini imzalama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Office applications, signing manifests
- deploying applications [ClickOnce], signing manifests
- deploying applications, signing manifests
- ClickOnce deployment, signing manifests
- Office development in Visual Studio, signing manifests
ms.assetid: d53bceb9-4d3b-4c22-b909-8f370e7231fb
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ba634ffb30d6459c940811f0ea080f8b71a37f34
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-re-sign-application-and-deployment-manifests"></a>Nasıl yapılır: Uygulama ve Dağıtım Bildirimlerini Yeniden İmzalama
Windows Forms uygulamaları, Windows Presentation Foundation uygulamaları (xbap) ya da Office çözümleri için uygulama bildiriminde dağıtım özelliklerini değişiklikleri yaptıktan sonra her iki uygulamayı yeniden imzalamak gerekir ve dağıtım bildirimlerini ile bir Sertifika. Bu işlem, son kullanıcı bilgisayarlarında değiştirilen dosyaların yüklü değil sağlamaya yardımcı olur.  
  
 Burada bildirimleri yeniden imzalayabilir başka bir müşterilerinizin uygulamayı imzalamak ve kendi sertifika ile dağıtım bildirimleri istediğinizde bir senaryodur.  
  
## <a name="re-signing-the-application-and-deployment-manifests"></a>Uygulama ve dağıtım bildirimlerini yeniden imzalama  
 Bu yordam, uygulama bildirim dosyasının (.manifest) değişiklikleri önceden yaptığınızı varsayar. Daha fazla bilgi için bkz: [nasıl yapılır: dağıtım özelliklerini değiştirme](http://msdn.microsoft.com/en-us/66052a3a-8127-4964-8147-2477ef5d1472).  
  
#### <a name="to-re-sign-the-application-and-deployment-manifests-with-mageexe"></a>Bildirimlerini Mage.exe ile uygulama ve dağıtım yeniden imzalamak için  
  
1.  Açık bir **Visual Studio komut istemi** penceresi.  
  
2.  Dizinleri imzalamak istediğiniz bildirim dosyalarını içeren klasöre gidin.  
  
3.  Bildirim dosyasını imzalamak için aşağıdaki komutu yazın. ManifestFileName'i bildirim dosyanızı artı uzantısı adı ile değiştirin. Sertifika dosyası göreli veya tam yoluna sahip sertifikayı değiştirin ve parola sertifikanın parolasını değiştirin.  
  
    ```  
    mage -sign ManifestFileName.manifest -CertFile Certificate -Password Password  
    ```  
  
     Örneğin, bir eklenti, bir Windows Form uygulaması veya bir Windows Presentation Foundation tarayıcı uygulaması için uygulama bildiriminizi imzalamak için aşağıdaki komutu çalıştırabilirsiniz. Visual Studio tarafından oluşturulan geçici sertifikalar üretim ortamları içine dağıtımı için önerilmez.  
  
    ```  
    mage -sign WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -sign ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -sign WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
4.  Güncelleştirme ve önceki adımla yer tutucu adlarını değiştirerek dağıtım bildirim dosyasını imzalamak için aşağıdaki komutu yazın.  
  
    ```  
    mage -update DeploymentManifest -appmanifest ApplicationManifest -CertFile Certificate -Password Password  
    ```  
  
     Örneğin, güncelleştirme ve Excel eklentisi, bir Windows Forms uygulaması veya bir Windows Presentation Foundation tarayıcı uygulaması için dağıtım bildirimini imzalamak için aşağıdaki komutu çalıştırabilirsiniz.  
  
    ```  
    mage -update WindowsFormsApplication1.application -appmanifest WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -update ExcelAddin1.vsto -appmanifest ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -update WpfBrowserApplication1.xbap -appmanifest WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
5.  İsteğe bağlı olarak, ana dağıtım bildirimini kopyalayın (Yayımlama\\*appname*.application) sürüm dağıtım dizinine (publish\Application dosyaları\\*appname*_ *sürüm*).  
  
## <a name="updating-and-re-signing-the-application-and-deployment-manifests"></a>Güncelleştirme ve uygulama ve dağıtım bildirimlerini yeniden imzalama  
 Bu yordam, bildirim dosyası (.manifest) uygulamanızda değişiklik yapılması zaten yapmış olduğunuz ancak güncelleştirildi diğer dosyaları olduğunu varsayar. Dosyalar güncelleştirildiğinde, dosyayı temsil eden karma da güncelleştirilmelidir.  
  
#### <a name="to-update-and-re-sign-the-application-and-deployment-manifests-with-mageexe"></a>Bildirimlerini Mage.exe ile güncelleştirmek ve uygulama ve dağıtım yeniden imzalamak için  
  
1.  Açık bir **Visual Studio komut istemi** penceresi.  
  
2.  Dizinleri imzalamak istediğiniz bildirim dosyalarını içeren klasöre gidin.  
  
3.  Yayımla çıktı klasöründeki dosyaları .deploy dosya uzantısını kaldırın.  
  
4.  Güncelleştirilen dosyaların yeni karmalar ile uygulama bildirimini güncelleştirmek ve uygulama bildirim dosyasının imzalamak için aşağıdaki komutu yazın. ManifestFileName'i bildirim dosyanızı artı uzantısı adı ile değiştirin. Sertifika dosyası göreli veya tam yoluna sahip sertifikayı değiştirin ve parola sertifikanın parolasını değiştirin.  
  
    ```  
    mage -update ManifestFileName.manifest -CertFile Certificate -Password Password  
    ```  
  
     Örneğin, bir eklenti, bir Windows Form uygulaması veya bir Windows Presentation Foundation tarayıcı uygulaması için uygulama bildiriminizi imzalamak için aşağıdaki komutu çalıştırabilirsiniz. Visual Studio tarafından oluşturulan geçici sertifikalar üretim ortamları içine dağıtımı için önerilmez.  
  
    ```  
    mage -update WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -update ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -update WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
5.  Güncelleştirme ve önceki adımla yer tutucu adlarını değiştirerek dağıtım bildirim dosyasını imzalamak için aşağıdaki komutu yazın.  
  
    ```  
    mage -update DeploymentManifest -appmanifest ApplicationManifest -CertFile Certificate -Password Password  
    ```  
  
     Örneğin, güncelleştirme ve Excel eklentisi, bir Windows Forms uygulaması veya bir Windows Presentation Foundation tarayıcı uygulaması için dağıtım bildirimini imzalamak için aşağıdaki komutu çalıştırabilirsiniz.  
  
    ```  
    mage -update WindowsFormsApplication1.application -appmanifest WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -update ExcelAddin1.vsto -appmanifest ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -update WpfBrowserApplication1.xbap -appmanifest WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
6.  Uygulama ve dağıtım bildirimi dışındaki dosyalara .deploy dosya uzantısını dosyaları geri ekleyin.  
  
7.  İsteğe bağlı olarak, ana dağıtım bildirimini kopyalayın (Yayımlama\\*appname*.application) sürüm dağıtım dizinine (publish\Application dosyaları\\*appname*_ *sürüm*).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md)   
 [ClickOnce uygulamaları için kod erişimi güvenliği](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce ve Authenticode](../deployment/clickonce-and-authenticode.md)   
 [Güvenilir Uygulama dağıtımına genel bakış](../deployment/trusted-application-deployment-overview.md)   
 [Nasıl yapılır: ClickOnce güvenlik ayarlarını etkinleştir](../deployment/how-to-enable-clickonce-security-settings.md)   
 [Nasıl yapılır: ClickOnce uygulaması için bir güvenlik bölgesi ayarlama](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)   
 [Nasıl yapılır: ClickOnce uygulaması için özel izinleri ayarlama](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [Nasıl yapılır: sınırlı izinler ile ClickOnce uygulamasında hata ayıklama](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [Nasıl yapılır: ClickOnce uygulamaları için bir istemci bilgisayara güvenilir bir yayımcı Ekle](../deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications.md)   
 [Nasıl yapılır: ClickOnce Güven İstemi Davranışını Yapılandırma](../deployment/how-to-configure-the-clickonce-trust-prompt-behavior.md)