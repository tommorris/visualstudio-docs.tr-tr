---
title: 'İzlenecek yol: ClickOnce uygulaması için özel bir yükleyici oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, custom installer
- installer [ClickOnce], custom
- deploying applications [ClickOnce], custom installer
- InPlaceHostingManager [ClickOnce], custom installer
- custom installer [ClickOnce]
ms.assetid: fb222cc5-8aeb-4b94-8c49-b93e342f5f69
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cdef0199aa55d6981761a20804f9f209a1a0fdc4
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="walkthrough-creating-a-custom-installer-for-a-clickonce-application"></a>İzlenecek Yol: ClickOnce Uygulaması için Özel bir Yükleyici Oluşturma
Bir .exe dosyasına dayalı herhangi bir ClickOnce uygulaması sessizce yüklü ve özel bir yükleyici tarafından güncelleştirilir. Özel bir yükleyici, özel iletişim kutuları için güvenlik ve bakım işlemleri dahil olmak üzere, yüklemesi sırasında özel bir kullanıcı deneyimi uygulayabilirsiniz. Özel yükleyici yükleme işlemlerini gerçekleştirmek için kullandığı <xref:System.Deployment.Application.InPlaceHostingManager> sınıfı. Bu kılavuzda nasıl sessizce bir ClickOnce uygulamasını yükleyen özel bir yükleyici oluşturulacağını gösterir.  
  
## <a name="prerequisites"></a>Önkoşullar  
  
### <a name="to-create-a-custom-clickonce-application-installer"></a>Özel bir ClickOnce Uygulama yükleyici oluşturmak için  
  
1.  ClickOnce uygulamanızda System.Deployment'a ve System.Windows.Forms ekleyin.  
  
2.  Uygulamanız için yeni bir sınıf ekleyin ve herhangi bir ad belirtin. Bu kılavuzda adı kullanılır `MyInstaller`.  
  
3.  Aşağıdakileri ekleyin `Imports` veya `using` yeni sınıfınıza üstüne deyimleri.  
  
    ```vb  
    Imports System.Deployment.Application  
    Imports System.Windows.Forms  
    ```  
  
    ```csharp  
    using System.Deployment.Application;  
    using System.Windows.Forms;  
    ```  
  
4.  Sınıfınıza aşağıdaki yöntemi ekleyin.  
  
     Bu yöntemleri <xref:System.Deployment.Application.InPlaceHostingManager> dağıtım bildirimi yükleme yöntemleri assert uygun izinleri yükleyin ve ardından uygulamayı indirmek ve ClickOnce önbelleğine yüklemek için kullanıcı izni isteyin. Özel yükleyici ClickOnce uygulaması önceden güvenilir olduğunu veya güven kararını erteleneceği belirtebilirsiniz <xref:System.Deployment.Application.InPlaceHostingManager.AssertApplicationRequirements%2A> yöntem çağrısı. Bu kod uygulamaya önceden güvenir.  
  
    > [!NOTE]
    >  Önceden güvenme ile atanan izinler özel yükleyici kodunun izinlerini aşamaz.  
  
     [!code-vb[System.Deployment.Application.InPlaceHostingManager#1](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-installer-for-a-clickonce-application_1.vb)]
     [!code-csharp[System.Deployment.Application.InPlaceHostingManager#1](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-installer-for-a-clickonce-application_1.cs)]  
  
5.  Kodunuzdan yükleme girişiminde çağrı `InstallApplication` yöntemi. Örneğin, sınıfınıza adlı `MyInstaller`, deniyor olabilir `InstallApplication` şu şekilde.  
  
    ```vb  
    Dim installer As New MyInstaller()  
    installer.InstallApplication("\\myServer\myShare\myApp.application")  
    MessageBox.Show("Installer object created.")  
    ```  
  
    ```csharp  
    MyInstaller installer = new MyInstaller();  
    installer.InstallApplication(@"\\myServer\myShare\myApp.application");  
    MessageBox.Show("Installer object created.");  
    ```  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 ClickOnce uygulaması güncelleştirme işlemi sırasında göstermek için bir özel kullanıcı arabirimi içeren özel güncelleştirme mantığı da ekleyebilirsiniz. Daha fazla bilgi için bkz. <xref:System.Deployment.Application.UpdateCheckInfo>. ClickOnce uygulaması ayrıca standart Başlat menüsü girdisi, kısayol ve Program Ekle veya Kaldır giriş kullanarak gizleyebilirsiniz bir `<customUX>` öğesi. Daha fazla bilgi için bkz: [ \<entryPoint > öğesi](../deployment/entrypoint-element-clickonce-application.md) ve <xref:System.Deployment.Application.DownloadApplicationCompletedEventArgs.ShortcutAppId%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulama bildirimi](../deployment/clickonce-application-manifest.md)   
 [\<entryPoint > öğesi](../deployment/entrypoint-element-clickonce-application.md)