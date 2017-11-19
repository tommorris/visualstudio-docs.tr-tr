---
title: "Nasıl yapılır: çalışma kodu bir SharePoint projesi dağıtıldığında veya geri çekildiğinde olduğu | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, extending deployment
ms.assetid: 353bbe6d-9b76-48ad-9fba-7e3c3712452f
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0650bfdb7961728fed34147c05f6333d8255e373
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-run-code-when-a-sharepoint-project-is-deployed-or-retracted"></a>Nasıl yapılır: Bir SharePoint Projesi Dağıtıldığında veya Geri Çekildiğinde Kodu Çalıştırma
  Bir SharePoint projesi dağıtıldığında veya geri çekilebilir ek görevleri gerçekleştirmek istiyorsanız, Visual Studio tarafından oluşturulan olayları işleyebilirsiniz. Daha fazla bilgi için bkz: [genişletme SharePoint paketleme ve dağıtım](../sharepoint/extending-sharepoint-packaging-and-deployment.md).  
  
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
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnekte aşağıdaki derlemelere başvuruları gerektirir:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>Uzantısını dağıtma  
 Uzantıyı dağıtmak için oluşturma bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] uzantısı (VSIX) paketini derleme ve uzantısıyla dağıtmak istediğiniz diğer dosyalar için. Daha fazla bilgi için bkz: [dağıtma uzantıları Visual Studio'da SharePoint araçları için](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletme SharePoint paketleme ve dağıtma](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [Nasıl yapılır: çalışma zaman dağıtım adımları yürütüldüğünde kodu](../sharepoint/how-to-run-code-when-deployment-steps-are-executed.md)  
  
  