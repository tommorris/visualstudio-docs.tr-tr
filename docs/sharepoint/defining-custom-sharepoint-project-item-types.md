---
title: Özel SharePoint proje öğesi türlerini tanımlama | Microsoft Docs
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
ms.openlocfilehash: 180d7e4878ca0c9493c949eac055713212c964de
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36326172"
---
# <a name="define-custom-sharepoint-project-item-types"></a>Özel SharePoint proje öğesi türlerini tanımlama
  Yeni tür bir SharePoint proje öğesi oluşturmak istediğiniz zaman yeni bir SharePoint proje öğesi türünü tanımlayın. Örneğin, Visual Studio alanlar ekleyerek veya bir SharePoint sitesine özel eylemler için SharePoint Proje öğeleri içermez. Kendi türlerde alanları, özel eylemler veya diğer tür SharePoint bileşenlerin oluşturmak için SharePoint Proje öğeleri tanımlayabilirsiniz.  
  
## <a name="tasks-for-defining-sharepoint-project-item-types"></a>SharePoint proje öğesi türlerini tanımlama için görevler
 Özel proje öğesi türünü tanımlamak için uygulayan bir Visual Studio uzantısı derleme <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> arabirimi. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint proje öğesi türü tanımlama](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).  
  
 Özel proje öğesi türü tanımladığınızda, proje öğesi için aşağıdaki işlevler de ekleyebilirsiniz:  
  
-   Bir kısayol menü öğesi için proje öğesi ekleyin. Proje öğesi için kısayol menüsünü açtığınızda menü öğesi görünür **Çözüm Gezgini** proje öğesi sağ tıklanarak veya seçip ardından seçme **Shift** +  **F10** anahtarları. Daha fazla bilgi için bkz: [nasıl yapılır: özel bir SharePoint Proje öğe türüne bir kısayol menü öğesi ekleme](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md).  
  
-   Bir özel özellik için proje öğesi ekleyin. Özellik görünür **özellikleri** proje öğesi seçtiğinizde penceresi **Çözüm Gezgini**. Daha fazla bilgi için bkz: [nasıl yapılır: özel bir SharePoint Proje öğe türüne özellik ekleme](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md).  
  
 Diğer geliştiriciler Visual Studio Proje öğesi kullanmak üzere etkinleştirmek için bir .spdata dosyası oluşturun ve bir öğe şablonu veya proje öğesi ile ilişkilendirilen proje şablonu oluşturun. Daha fazla bilgi için bkz: [öğe şablonları ve SharePoint Proje öğeleri için proje şablonları oluşturma](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
## <a name="understand-the-relationship-between-project-item-types-and-project-item-instances"></a>Proje öğesi türleri ve proje öğesi örnekleri arasındaki ilişkiyi anlama
 Bir SharePoint Proje öğe türüne tanımladığınızda, ilişkili türünde bir proje öğesi bir SharePoint projesine eklenen uzantınızın Visual Studio yükler. Örneğin, yeni bir tanımlarsanız **özel eylem** öğesi proje türü, Visual Studio kullanıcı eklediğinde uzantınızı yükler bir **özel eylem** projeye proje öğesi. Visual Studio için tüm örneklerini ilişkili proje öğesi türü uzantınızı aynı örneğini kullanır. Önceki örnekte kullanıcı saniyenin eklerse **özel eylem** projeye proje madde, aynı örnek uzantınızın ikinci proje öğesi özelleştirmek için kullanılır.  
  
 Proje öğesi türü belirli bir örneğine erişmek için aşağıdakilerden birini ele <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> olayları *projectItemTypeDefinition* parametresi uygulamanızda <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> yöntemi. Örneğin, bir proje öğesi özel aynı türden bir projeye eklendiğinde belirlemek için tanıtıcı <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> olay. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint proje öğesi türü tanımlama](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).  
  
## <a name="see-also"></a>Ayrıca bkz.
 [Nasıl yapılır: bir SharePoint proje öğesi türü tanımlama](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)   
 [Nasıl yapılır: özel bir SharePoint Proje öğe türüne özellik ekleme](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)   
 [Nasıl yapılır: özel bir SharePoint Proje öğe türüne bir kısayol menü öğesi ekleme](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md)   
 [Öğe şablonları ve SharePoint Proje öğeleri için proje şablonları oluşturma](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [İzlenecek yol: bir öğe şablonu, bölüm 1 ile özel bir eylem proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [İzlenecek yol: bir proje şablonu, bölüm 1 ile site sütunu proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)   
 [İzlenecek yol: bir öğe şablonu, bölüm 2 ile özel bir eylem proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)   
 [İzlenecek yol: bir proje şablonu, bölüm 2 ile bir site sütunu proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)   
 [Visual Studio'da SharePoint araçları için uzantıları dağıtma](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
