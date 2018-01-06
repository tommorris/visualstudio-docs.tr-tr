---
title: "Nasıl yapılır: çalışma zaman dağıtım adımları yürütüldüğünde kodu | Microsoft Docs"
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
ms.assetid: 6b0a52e5-e0ba-41bc-9e8a-1013e51fd3ba
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: a147b9f6def49565334004bda1f8c4c80b0e7bfa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-run-code-when-deployment-steps-are-executed"></a>Nasıl yapılır: Dağıtım Adımları Yürütüldüğünde Kodu Çalıştırma
  Bir SharePoint projesine bir dağıtım adımı için ek görevleri gerçekleştirmek istiyorsanız, önce SharePoint Proje öğeleri ve her dağıtım adımı Visual Studio yürütüldükten sonra gerçekleştirilen olayları işleyebilirsiniz. Daha fazla bilgi için bkz: [genişletme SharePoint paketleme ve dağıtım](../sharepoint/extending-sharepoint-packaging-and-deployment.md).  
  
### <a name="to-run-code-when-deployment-steps-are-executed"></a>Dağıtım adımları yürütüldüğünde kodu çalıştırmak için  
  
1.  Bir proje öğesi uzantısı, bir proje uzantısı veya yeni bir proje öğesi türü tanımı oluşturun. Daha fazla bilgi için aşağıdaki konulara bakın:  
  
    -   [Nasıl yapılır: Bir SharePoint Proje Öğesi Uzantısı Oluşturma](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)  
  
    -   [Nasıl yapılır: Bir SharePoint Proje Uzantısı Oluşturma](../sharepoint/how-to-create-a-sharepoint-project-extension.md)  
  
    -   [Nasıl yapılır: Bir SharePoint Proje Öğesi Türü Tanımlama](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)  
  
2.  Uzantısı'nda ele <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> ve <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepCompleted> olayların bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType> nesnesi (bir proje öğesi uzantısı veya proje uzantısı) veya bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition> nesnesinde (yeni bir proje öğesi türü tanımını).  
  
3.  Olay işleyicilerini kullanmak <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepStartedEventArgs> ve <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepCompletedEventArgs> dağıtım adım hakkında bilgi almak için parametreler. Örneğin, hangi dağıtım adımı yürütme ve çözümü olup yapılıyor belirleyebilirsiniz dağıtıldığında veya geri çekilebilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde nasıl işleneceğini gösterir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> ve <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepCompleted> listesi örneği proje öğesi için bir uzantı olayları. Bu uzantı için ek bir ileti yazar **çıkış** dağıtma ve çözüm geri çekilen Visual Studio uygulama havuzu dönüştürüldüğünde penceresi.  
  
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#4](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/handledeploymentstepevents.vb#4)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#4](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/handledeploymentstepevents.cs#4)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnekte aşağıdaki derlemelere başvuruları gerektirir:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>Uzantısını dağıtma  
 Uzantıyı dağıtmak için oluşturma bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] uzantısı (VSIX) paketini derleme ve uzantısıyla dağıtmak istediğiniz diğer dosyalar için. Daha fazla bilgi için bkz: [dağıtma uzantıları Visual Studio'da SharePoint araçları için](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletme SharePoint paketleme ve dağıtma](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [İzlenecek yol: SharePoint projeleri için özel bir dağıtım adımı oluşturma](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)   
 [Nasıl yapılır: Bir SharePoint Projesi Dağıtıldığında veya Geri Çekildiğinde Kodu Çalıştırma](../sharepoint/how-to-run-code-when-a-sharepoint-project-is-deployed-or-retracted.md)  
  
  