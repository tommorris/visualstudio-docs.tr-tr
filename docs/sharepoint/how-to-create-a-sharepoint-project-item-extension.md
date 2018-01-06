---
title: "Nasıl yapılır: bir SharePoint proje öğesi uzantısı oluşturma | Microsoft Docs"
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
helpviewer_keywords:
- project items [SharePoint development in Visual Studio], extending
- SharePoint project items, extending
- SharePoint development in Visual Studio, extending project items
ms.assetid: 163738b9-e25a-49c9-8f33-4b57a2da6b07
caps.latest.revision: "31"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: b927b71e33ab6a26729a2db9190e2755eee092a6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-sharepoint-project-item-extension"></a>Nasıl yapılır: Bir SharePoint Proje Öğesi Uzantısı Oluşturma
  Visual Studio'da zaten yüklenmiş bir SharePoint proje öğesi işlevselliği eklemek istediğinizde bir proje öğesi uzantısı oluşturma. Daha fazla bilgi için bkz: [SharePoint proje öğelerini genişletme](../sharepoint/extending-sharepoint-project-items.md).  
  
### <a name="to-create-a-project-item-extension"></a>Bir proje öğesi uzantısı oluşturmak için  
  
1.  Bir sınıf kitaplığı projesi oluşturun.  
  
2.  Aşağıdaki derlemelere başvurular ekleyin:  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   System.ComponentModel.Composition  
  
3.  Arabirimini uygulayan bir sınıf oluşturun <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> arabirimi.  
  
4.  Aşağıdaki öznitelikler sınıfına ekleyin:  
  
    -   <xref:System.ComponentModel.Composition.ExportAttribute>. Bu öznitelik bulmak ve yüklemek Visual Studio sağlar, <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> uygulaması. Geçirmek <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> öznitelik oluşturucunun türü.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>. Bu öznitelik bir proje öğesi uzantısı, genişletmek istediğiniz proje öğesi tanımlar. Proje öğesi kimliği özniteliği oluşturucuya geçirin. Visual Studio ile birlikte proje öğeleri kimliklerinin bir listesi için bkz [SharePoint proje öğelerini genişletme](../sharepoint/extending-sharepoint-project-items.md).  
  
5.  Uygulamanızda <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> yöntemi, kullanım üyeleri *projectItemType* uzantınızı davranışını tanımlamak için parametre. Bu parametre bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType> tanımlanan olayları erişimi sağlayan nesne <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> ve <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFileEvents> arabirimleri. Belirli bir örneği genişletme proje öğe türüne erişmek için tanıtıcı <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> olayları gibi <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> ve <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemInitialized>.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, basit bir olay alıcısına proje öğesi uzantısı oluşturma gösterilmiştir. Her kullanıcı bir SharePoint projesine bir olay alıcısına proje öğesi ekler, bu uzantı için bir ileti yazar **çıkış** penceresi ve **hata listesi** penceresi.  
  
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#1](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/projectitemextension.cs#1)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#1](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/projectitemextension.vb#1)]  
  
 Bu örnek ileti yazmak için SharePoint Proje hizmeti kullanır **çıkış** penceresi ve **hata listesi** penceresi. Daha fazla bilgi için bkz: [SharePoint Proje hizmetini kullanma](../sharepoint/using-the-sharepoint-project-service.md).  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnekte aşağıdaki derlemelere başvuruları gerektirir:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>Uzantısını dağıtma  
 Uzantıyı dağıtmak için oluşturma bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] uzantısı (VSIX) paketini derleme ve uzantısıyla dağıtmak istediğiniz diğer dosyalar için. Daha fazla bilgi için bkz: [dağıtma uzantıları Visual Studio'da SharePoint araçları için](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint proje öğelerini genişletme](../sharepoint/extending-sharepoint-project-items.md)   
 [İzlenecek yol: Bir SharePoint Proje Öğesi Türünü Genişletme](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)  
  
  