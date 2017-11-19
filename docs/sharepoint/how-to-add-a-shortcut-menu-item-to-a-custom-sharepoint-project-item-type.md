---
title: "Nasıl yapılır: özel SharePoint Proje öğe türüne bir kısayol menü öğesi ekleme | Microsoft Docs"
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
- SharePoint project items, defining your own types
- project items [SharePoint development in Visual Studio], defining your own types
- SharePoint development in Visual Studio, defining new project item types
ms.assetid: f6ec47a7-e7d9-4e26-810b-77943a1ab04c
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d0e8bdf4e0104b1358085107ffabb5d0c05d5924
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type"></a>Nasıl yapılır: Özel bir SharePoint Proje Öğe Türüne bir Kısayol Menü Öğesi Ekleme
  Özel bir SharePoint Proje öğe türüne tanımladığınızda, proje öğesi bir kısayol menü öğesi ekleyebilirsiniz. Bir kullanıcı proje öğeyi tıklattığında menü öğesi görünür **Çözüm Gezgini**.  
  
 Aşağıdaki adımlarda kendi SharePoint Proje öğe türüne önceden tanımlamış olduğunuz varsayılmaktadır. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint proje öğesi türü tanımlama](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).  
  
### <a name="to-add-a-shortcut-menu-item-to-a-custom-project-item-type"></a>Bir özel Proje öğe türüne bir kısayol menü öğesi eklemek için  
  
1.  İçinde <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> yöntemi, <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> uygulaması, tanıtıcı <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> olayı *projectItemTypeDefinition* parametresi.  
  
2.  Olay işleyicisi için <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> olay, yeni bir ekleme <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> nesnesini <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.ViewMenuItems%2A> veya <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.AddMenuItems%2A> olay bağımsız değişken parametre koleksiyonu.  
  
3.  İçinde <xref:Microsoft.VisualStudio.SharePoint.IMenuItem.Click> yeni için olay işleyicisini <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> nesne, bir kullanıcı kısayol menü öğesi seçtiğinde yürütmek istediğiniz görevleri gerçekleştirin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, bir özel proje öğesi türü için bir bağlam menüsü öğesini eklemek gösterilmiştir. Kullanıcı açtığında kısayol menüsünün Proje öğesinden **Çözüm Gezgini** ve seçer **yazma iletisi çıkış penceresine** menü öğesi, Visual Studio içinde bir ileti görüntüler **çıkış**  penceresi.  
  
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#4](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemtypemenu.cs#4)]
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#4](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemtypemenu.vb#4)]  
  
 Bu örnek ileti yazmak için SharePoint Proje hizmeti kullanır **çıkış** penceresi. Daha fazla bilgi için bkz: [SharePoint Proje hizmetini kullanma](../sharepoint/using-the-sharepoint-project-service.md).  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek, bir sınıf kitaplığı projesi aşağıdaki derlemeler başvuruları gerektirir:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-project-item"></a>Proje öğesi dağıtma  
 Proje öğesi kullanmak diğer geliştiriciler etkinleştirmek için bir proje şablonu veya bir proje öğesi şablonu oluşturun. Daha fazla bilgi için bkz: [öğe şablonları oluşturma ve SharePoint Proje öğeleri için proje şablonları](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
 Proje öğesi dağıtmak için Oluştur bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] uzantısı (VSIX) paketini derleme, şablonun ve proje öğesi ile dağıtmak istediğiniz diğer tüm dosyalar. Daha fazla bilgi için bkz: [dağıtma uzantıları Visual Studio'da SharePoint araçları için](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir SharePoint proje öğesi türü tanımlama](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)   
 [Nasıl yapılır: özel SharePoint Proje öğe türüne özellik ekleme](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)   
 [Özel SharePoint proje öğesi türlerini tanımlama](../sharepoint/defining-custom-sharepoint-project-item-types.md)  
  
  