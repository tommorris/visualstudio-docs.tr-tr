---
title: "Nasıl yapılır: dağıtım çakışmalarını işleme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SharePoint development in Visual Studio, extending deployment
ms.assetid: 8e545873-3fed-46cf-a95f-27b5fc0d5f83
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: c908262a0ff74bb8574fd76f788611165934375b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-handle-deployment-conflicts"></a>Nasıl yapılır: Dağıtım Çakışmalarını İşleme
  Bir SharePoint proje öğesi için dağıtım çakışmaları işlemek için kendi kodunuzu sağlayabilir. Örneğin, geçerli proje öğesi klasördeki tüm dosyaları konumunda zaten var ve geçerli proje öğesi dağıtılmadan önce dağıtılan dosyaları sil olup olmadığını belirleyebilirsiniz. Dağıtım çakışmaları hakkında daha fazla bilgi için bkz: [genişletme SharePoint paketleme ve dağıtım](../sharepoint/extending-sharepoint-packaging-and-deployment.md).  
  
### <a name="to-handle-a-deployment-conflict"></a>Dağıtım çakışma işlemek için  
  
1.  Bir proje öğesi uzantısı, bir proje uzantısı veya yeni bir proje öğesi türü tanımı oluşturun. Daha fazla bilgi için aşağıdaki konulara bakın:  
  
    -   [Nasıl yapılır: Bir SharePoint Proje Öğesi Uzantısı Oluşturma](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)  
  
    -   [Nasıl yapılır: Bir SharePoint Proje Uzantısı Oluşturma](../sharepoint/how-to-create-a-sharepoint-project-extension.md)  
  
    -   [Nasıl yapılır: Bir SharePoint Proje Öğesi Türü Tanımlama](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)  
  
2.  Uzantısı'nda ele <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> olayı bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType> nesnesi (bir proje öğesi uzantısı veya proje uzantısı) veya bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition> nesnesinde (yeni bir proje öğesi türü tanımını).  
  
3.  Olay işleyicisi dağıtılmakta olan proje öğesi ve senaryonuz için geçerli ölçütlere göre dağıtılan çözümü SharePoint sitesinde arasında bir çakışma olup olmadığını belirler. Kullanabileceğiniz <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemEventArgs.ProjectItem%2A> dağıtılmakta olan proje öğesi çözümlemek için olay bağımsız değişkenleri parametresinin özelliğini ve analiz dağıtım konumundaki dosyaları bu amaç için tanımladığınız bir SharePoint komutu çağırarak.  
  
     Çakışma birçok türleri için önce belirlemek hangi dağıtım adımı yürütme isteyebilirsiniz. Kullanarak bunu yapabilirsiniz <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepStartedEventArgs.DeploymentStepInfo%2A> olay bağımsız değişkenleri parametresinin özelliği sağlar. Genellikle yerleşik sırasında çakışmaları algılamaya mantıklıdır rağmen <xref:Microsoft.VisualStudio.SharePoint.Deployment.DeploymentStepIds.AddSolution> dağıtım adımı çakışmalar için herhangi bir dağıtım adımı sırasında denetleyebilirsiniz.  
  
4.  Bir çakışma varsa, kullanmak <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflictCollection.Add%2A> yöntemi <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepStartedEventArgs.Conflicts%2A> yeni olay bağımsız değişkenlerinin özelliği <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflict> nesnesi. Bu nesne dağıtım çakışma temsil eder. Aramanız için de <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflictCollection.Add%2A> yöntemi, ayrıca çakışmayı çözmek için çağrılan yöntemi belirtin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde bir proje öğesi uzantısı listesi tanımı proje öğeleri için bir dağıtım çakışma işlemek için temel işlemi gösterilmektedir. Farklı bir proje öğesi türü için bir dağıtım çakışması işlemek için farklı bir dizeyi geçirmek <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>. Daha fazla bilgi için bkz: [SharePoint proje öğelerini genişletme](../sharepoint/extending-sharepoint-project-items.md).  
  
 Basitleştirmek için <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> olay işleyicisi Bu örnekte, bir dağıtım çakışma bulunduğunu varsayar (diğer bir deyişle, her zaman yeni bir ekler <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflict> nesnesi) ve `Resolve` yöntemi yalnızca döndürür **true** belirtmek için çakışma çözüldü. Gerçek bir senaryoda, <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> olay işleyicisi geçerli proje öğesi bir dosyanız ve bir dağıtım konumundaki arasında bir çakışma varsa, ilk belirleyin ve ardından ekleyin bir <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflict> yalnızca bir çakışma var olup olmadığını nesne. Örneğin, kullanabilirsiniz `e.ProjectItem.Files` proje öğesi ve dosyaları çözümlemek için olay işleyicisini özelliğinde dağıtım konumundaki dosyaları çözümlemek için bir SharePoint komutu çağrısı. Benzer şekilde, gerçek bir senaryoda `Resolve` yöntemi SharePoint sitesinde çakışmayı çözmek için SharePoint komutu çağrısı. SharePoint komutları oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint komutu oluşturma](../sharepoint/how-to-create-a-sharepoint-command.md).  
  
 [!code-vb[SPExtensibility.ProjectItemExtension.DeploymentConflict#1](../sharepoint/codesnippet/VisualBasic/deploymentconflict/extension/deploymentconflictextension.vb#1)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.DeploymentConflict#1](../sharepoint/codesnippet/CSharp/deploymentconflict/extension/deploymentconflictextension.cs#1)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnekte aşağıdaki derlemelere başvuruları gerektirir:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>Uzantısını dağıtma  
 Uzantıyı dağıtmak için oluşturma bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] uzantısı (VSIX) paketini derleme ve uzantısıyla dağıtmak istediğiniz diğer dosyalar için. Daha fazla bilgi için bkz: [dağıtma uzantıları Visual Studio'da SharePoint araçları için](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletme SharePoint paketleme ve dağıtma](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [SharePoint proje öğelerini genişletme](../sharepoint/extending-sharepoint-project-items.md)   
 [Nasıl yapılır: çalışma zaman dağıtım adımları yürütüldüğünde kodu](../sharepoint/how-to-run-code-when-deployment-steps-are-executed.md)   
 [Nasıl yapılır: Bir SharePoint Komutu Oluşturma](../sharepoint/how-to-create-a-sharepoint-command.md)  
  
  