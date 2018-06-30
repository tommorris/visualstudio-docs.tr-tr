---
title: 'Nasıl yapılır: çalışma kodu bir SharePoint projesi dağıtıldığında veya geri çekildiğinde olduğu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, extending deployment
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4fa7d2652e65e26686a5058fcb2c8f5130fbbdde
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120568"
---
# <a name="how-to-run-code-when-a-sharepoint-project-is-deployed-or-retracted"></a>Nasıl yapılır: bir SharePoint projesi dağıtıldığında veya geri çekilebilir kodu çalıştırma
  Bir SharePoint projesi dağıtıldığında veya geri çekilebilir ek görevleri gerçekleştirmek istiyorsanız, Visual Studio tarafından oluşturulan olayları işleyebilirsiniz. Daha fazla bilgi için bkz: [genişletmek SharePoint paketleme ve dağıtım](../sharepoint/extending-sharepoint-packaging-and-deployment.md).  
  
### <a name="to-run-code-when-a-sharepoint-project-is-deployed-or-retracted"></a>Bir SharePoint proje kodunu çalıştırmak için dağıtıldığında geri çekilebilir veya  
  
1.  Bir proje öğesi uzantısı, bir proje uzantısı veya yeni bir proje öğesi türü tanımı oluşturun. Daha fazla bilgi için aşağıdaki konulara bakın:  
  
    -   [Nasıl yapılır: bir SharePoint proje öğesi uzantısı oluşturma](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)  
  
    -   [Nasıl yapılır: bir SharePoint proje uzantısı oluşturma](../sharepoint/how-to-create-a-sharepoint-project-extension.md)  
  
    -   [Nasıl yapılır: bir SharePoint proje öğesi türü tanımlama](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)  
  
2.  Uzantı, erişim <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> nesnesi. Daha fazla bilgi için bkz: [nasıl yapılır: SharePoint Proje hizmetini alma](../sharepoint/how-to-retrieve-the-sharepoint-project-service.md).  
  
3.  İşleme <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.DeploymentStarted> ve <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.DeploymentCompleted> proje hizmeti olayları.  
  
4.  Olay işleyicilerini kullanmak <xref:Microsoft.VisualStudio.SharePoint.DeploymentEventArgs> geçerli dağıtım oturumu hakkında bilgi almak için parametre. Örneğin, geçerli dağıtım oturumda hangi projedir ve olup yapılıyor belirleyebilirsiniz dağıtıldığında veya geri çekilebilir.  
  
 Aşağıdaki kod örneğinde nasıl işleneceğini gösterir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.DeploymentStarted> ve <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.DeploymentCompleted> proje uzantı olayları. Bu uzantı için ek bir ileti yazar **çıkış** dağıtımı başlar ve bir SharePoint proje için tamamlandıktan penceresi.  
  
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#12](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/handleprojectdeploymentevents.cs#12)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#12](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/handleprojectdeploymentevents.vb#12)]  
  
## <a name="compile-the-code"></a>Kod derleme  
 Bu örnekte aşağıdaki derlemelere başvuruları gerektirir:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploy-the-extension"></a>Uzantısı dağıtma  
 Uzantıyı dağıtmak için oluşturma bir [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] uzantısı (VSIX) paketini derleme ve uzantısıyla dağıtmak istediğiniz diğer dosyalar için. Daha fazla bilgi için bkz: [Visual Studio'da SharePoint araçları için Uzantılar dağıtmak](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca bkz.
 [SharePoint paketleme ve dağıtımını genişletme](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [Nasıl yapılır: dağıtım adımları yürütüldüğünde kodu çalıştırma](../sharepoint/how-to-run-code-when-deployment-steps-are-executed.md)  
  
