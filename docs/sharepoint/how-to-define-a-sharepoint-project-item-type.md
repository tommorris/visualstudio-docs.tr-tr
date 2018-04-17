---
title: 'Nasıl yapılır: bir SharePoint proje öğesi türü tanımlama | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project items, defining your own types
- project items [SharePoint development in Visual Studio], defining your own types
- SharePoint development in Visual Studio, defining new project item types
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4a0470e84b6c85fdb0786cdee27a2d208a594c0d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-define-a-sharepoint-project-item-type"></a>Nasıl yapılır: Bir SharePoint Proje Öğesi Türü Tanımlama
  Özel bir SharePoint proje öğesi oluşturmak istediğinizde bir proje öğesi türünü tanımlayın. Daha fazla bilgi için bkz: [özel SharePoint proje öğesi türlerini tanımlama](../sharepoint/defining-custom-sharepoint-project-item-types.md).  
  
### <a name="to-define-a-project-item-type"></a>Bir proje öğesi türünü tanımlamak için  
  
1.  Bir sınıf kitaplığı projesi oluşturun.  
  
2.  Aşağıdaki derlemelere başvurular ekleyin:  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   System.ComponentModel.Composition  
  
3.  Arabirimini uygulayan bir sınıf oluşturun <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> arabirimi.  
  
4.  Aşağıdaki öznitelikler sınıfına ekleyin:  
  
    -   <xref:System.ComponentModel.Composition.ExportAttribute>. Bu öznitelik bulmak ve yüklemek Visual Studio sağlar, <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> uygulaması. Geçirmek <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> öznitelik oluşturucunun türü.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>. Proje öğesi türü tanımı üzerinde bu öznitelik yeni proje öğesi dize tanımlayıcısını belirtir. Biçimini kullanmanızı öneririz *şirket adı*. *özellik adı* tüm proje öğeleri benzersiz bir ad olduğundan emin olun yardımcı olmak için.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemIconAttribute>. Bu öznitelik bu proje öğesi için görüntülemek için bu simgeyi belirtir **Çözüm Gezgini**. Bu öznitelik isteğe bağlıdır; sınıfı, uygulamazsanız Visual Studio Proje öğesi için varsayılan bir simge görüntüler. Bu öznitelik ayarlarsanız, simge veya bütünleştirilmiş kodunda katıştırılmış bit eşlem tam adını geçirin.  
  
5.  Uygulamanızda <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> yöntemi, kullanım üyeleri *projectItemTypeDefinition* proje öğesi türü davranışını tanımlamak için parametre. Bu parametre bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition> tanımlanan olayları erişimi sağlayan nesne <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> ve <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFileEvents> arabirimleri. Proje öğesi türü belirli bir örneğine erişmek için tanıtıcı <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> olayları gibi <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> ve <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemInitialized>.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, bir Basit Proje öğesi türünü tanımlamak gösterilmiştir. Bu proje öğesi türü için bir ileti yazar **çıkış** penceresi ve **hata listesi** bir kullanıcı bir proje için bir proje öğesi bu türdeki eklediğinde penceresi.  
  
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#2](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/projectitemtype.vb#2)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#2](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/projectitemtype.cs#2)]  
  
 Bu örnek ileti yazmak için SharePoint Proje hizmeti kullanır **çıkış** penceresi ve **hata listesi** penceresi. Daha fazla bilgi için bkz: [SharePoint Proje hizmetini kullanma](../sharepoint/using-the-sharepoint-project-service.md).  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnekte aşağıdaki derlemelere başvuruları gerektirir:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-project-item"></a>Proje öğesi dağıtma  
 Proje öğesi kullanmak diğer geliştiriciler etkinleştirmek için bir proje şablonu veya bir proje öğesi şablonu oluşturun. Daha fazla bilgi için bkz: [öğe şablonları oluşturma ve SharePoint Proje öğeleri için proje şablonları](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
 Proje öğesi dağıtmak için Oluştur bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] uzantısı (VSIX) paketini derleme, şablonun ve proje öğesi ile dağıtmak istediğiniz diğer tüm dosyalar. Daha fazla bilgi için bkz: [dağıtma uzantıları Visual Studio'da SharePoint araçları için](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel SharePoint proje öğesi türlerini tanımlama](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [SharePoint Proje öğeleri için öğe şablonları ve proje şablonları oluşturma](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [İzlenecek yol: bir öğe şablonu, bölüm 1 ile bir özel eylem proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [İzlenecek yol: bir proje şablonu, bölüm 1 ile bir Site sütunu proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)   
 [Nasıl yapılır: özel SharePoint Proje öğe türüne özellik ekleme](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)   
 [Nasıl yapılır: Özel bir SharePoint Proje Öğe Türüne bir Kısayol Menü Öğesi Ekleme](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md)  
  
  