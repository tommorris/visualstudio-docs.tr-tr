---
title: "SharePoint proje öğelerini genişletme | Microsoft Docs"
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
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: e990896720916048ab449c7ccb5a927577861256
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="extending-sharepoint-project-items"></a>SharePoint Proje Öğelerini Genişletme
  Visual Studio'da yüklü SharePoint proje öğesi türü işlevselliği eklemek istediğinizde bir proje öğesi uzantısı oluşturma. Örneğin, bir uzantı yerleşik oluşturabilirsiniz **olay alıcısı** veya **listesi tanımını** proje öğelerini Visual Studio'da ya da bir özel proje öğesi türü için bir uzantı oluşturabilirsiniz. Tüm SharePoint proje öğesi türleri için bir uzantı de oluşturabilirsiniz.  
  
## <a name="tasks-for-extending-sharepoint-project-items"></a>SharePoint proje öğelerini genişletme için görevler  
 Bir proje öğesi genişletmek için uygulayan bir Visual Studio uzantısı derleme <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> arabirimi. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint proje öğesi uzantısı oluşturma](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md).  
  
 Bir proje öğesi genişlettiğinizde, proje öğesi için aşağıdaki işlevler de ekleyebilirsiniz:  
  
-   Bir kısayol menü öğesi için proje öğesi ekleyin. Proje öğesi için kısayol menüsünü açtığınızda menü öğesi görünür **Çözüm Gezgini**. Proje öğesi sağ tıklayarak kısayol menüsünü açın veya bunu seçerek ve ardından SHIFT + F10 tuşlarına. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint Proje öğe uzantısına bir kısayol menü öğesi ekleme](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-sharepoint-project-item-extension.md).  
  
-   Bir özel özellik için proje öğesi ekleyin. Özellik görünür **özellikleri** proje öğesi seçtiğinizde penceresi **Çözüm Gezgini**. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint Proje öğe uzantısına özellik ekleme](../sharepoint/how-to-add-a-property-to-a-sharepoint-project-item-extension.md).  
  
 Oluşturma, dağıtma ve bir proje öğesi uzantısı test izlenecek yol için bkz: [izlenecek yol: bir SharePoint proje öğesi türünü genişletme](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md).  
  
## <a name="understanding-the-relationship-between-project-item-extensions-and-project-item-instances"></a>Project öğesi uzantıları ve proje öğesi örnekleri arasındaki ilişkiyi anlama  
 Bir proje öğesi uzantısı oluşturma, bir proje öğesi ilişkili türünde bir SharePoint projesine eklendiğinde, Visual Studio uzantınızı yükler. Örneğin, bir uzantı için oluşturursanız **olay alıcısı** proje öğeleri, Visual Studio yükler uzantınızı kullanıcı eklediğinde bir **olay alıcısı** projeye proje öğesi. Visual Studio için tüm örneklerini ilişkili proje öğesi türü uzantınızı aynı örneğini kullanır. Önceki örnekte kullanıcı saniyenin eklerse **olay alıcısı** projeye proje madde, aynı örnek uzantınızın ikinci proje öğesi özelleştirmek için kullanılır.  
  
 Belirli bir örneği genişletme proje öğe türüne erişmek için aşağıdakilerden birini ele <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> olayları *projectItemType* parametresi uygulamanızda <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> yöntemi. Örneğin, bir proje öğesi genişletme türü bir projeye eklendiğinde belirlemek için tanıtıcı <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> olay. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint proje öğesi uzantısı oluşturma](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md).  
  
## <a name="identifiers-for-sharepoint-project-items"></a>SharePoint Proje öğeleri için tanımlayıcıları  
 Her bir SharePoint Proje öğe karşılık gelen bir dize tanımlayıcısı vardır. Aşağıdaki görevleri gerçekleştirmek istiyorsanız, bir proje öğesi için tanımlayıcı bilmeniz gerekir:  
  
-   Proje öğesi için bir uzantı oluşturun. Bu durumda, tanımlayıcı oluşturucusuna genişletmek istediğiniz proje öğesi için geçmesi gereken <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>. Tüm türleri öğesi proje uzantı oluşturmak için geçirmek  **\***  dize değeri.  
  
-   Proje öğesi program aracılığıyla bir projeye ekleyin. Bu durumda, proje öğesi için tanımlayıcı geçmelidir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemCollection.Add%2A> yöntemi.  
  
 Aşağıdaki tabloda, Visual Studio ile birlikte SharePoint Proje öğeleri için tanımlayıcıları listeler.  
  
|Proje öğesi adı|Dize tanımlayıcı|  
|-----------------------|-----------------------|  
|İş Verileri Kataloğu modeli|Microsoft.VisualStudio.SharePoint.BusinessDataConnectivity|  
|İçerik türü|Microsoft.VisualStudio.SharePoint.ContentType|  
|Olay alıcısı|Microsoft.VisualStudio.SharePoint.EventHandler|  
|Boş öğesi|Microsoft.VisualStudio.SharePoint.GenericElement|  
|Liste tanımı<br /><br /> Liste tanımından içerik türü|Microsoft.VisualStudio.SharePoint.ListDefinition|  
|Liste örneği|Microsoft.VisualStudio.SharePoint.ListInstance|  
|Modül|Microsoft.VisualStudio.SharePoint.Module|  
|Sıralı iş akışı<br /><br /> Durum makinesi iş akışı|Microsoft.VisualStudio.SharePoint.Workflow|  
|Site tanımı|Microsoft.VisualStudio.SharePoint.SiteDefinition|  
|Visual Web Bölümü|Microsoft.VisualStudio.SharePoint.VisualWebPart|  
|Web Kısmı|Microsoft.VisualStudio.SharePoint.WebPart|  
|İş akışı ilişkilendirme formu|Microsoft.VisualStudio.SharePoint.WorkflowAssociation|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir SharePoint proje öğesi uzantısı oluşturma](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)   
 [Nasıl yapılır: bir SharePoint Proje öğe uzantısına bir kısayol menü öğesi ekleme](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-sharepoint-project-item-extension.md)   
 [Nasıl yapılır: bir SharePoint Proje öğe uzantısına özellik ekleme](../sharepoint/how-to-add-a-property-to-a-sharepoint-project-item-extension.md)   
 [İzlenecek yol: bir SharePoint proje öğesi türünü genişletme](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)   
 [SharePoint Proje Sistemini Genişletme](../sharepoint/extending-the-sharepoint-project-system.md)  
  