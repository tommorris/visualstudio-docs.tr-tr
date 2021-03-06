---
title: 'Nasıl yapılır: Sunucu Gezgininde SharePoint düğümünü genişletme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint Connections [SharePoint development in Visual Studio], extending a node
- SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1dee26ae729dedc2d38895ca84e430ffcbad875f
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120565"
---
# <a name="how-to-extend-a-sharepoint-node-in-server-explorer"></a>Nasıl yapılır: Sunucu Gezgininde SharePoint düğümünü genişletme
  Düğümleri altında genişletebilirsiniz **SharePoint bağlantıları** düğümünde **Sunucu Gezgini**. Yeni alt düğümleri, kısayol menüsü öğelerini ya da özellikler için varolan bir düğümü eklemek istediğinizde kullanışlıdır. Daha fazla bilgi için bkz: [Sunucu Gezgininde SharePoint bağlantıları düğümünü genişletme](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md).  
  
### <a name="to-extend-a-sharepoint-node-in-server-explorer"></a>Sunucu Gezgininde SharePoint düğümünü genişletmek için  
  
1.  Bir sınıf kitaplığı projesi oluşturun.  
  
2.  Aşağıdaki derlemelere başvurular ekleyin:  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   Microsoft.VisualStudio.SharePoint.Explorer.Extensions  
  
    -   System.ComponentModel.Composition  
  
3.  Arabirimini uygulayan bir sınıf oluşturun <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> arabirimi.  
  
4.  Ekleme <xref:System.ComponentModel.Composition.ExportAttribute> öznitelik sınıfı. Bu öznitelik bulmak ve yüklemek Visual Studio sağlar, <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> uygulaması. Geçirmek <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> öznitelik oluşturucunun türü.  
  
5.  Ekleme <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeTypeAttribute> öznitelik sınıfı. Bu öznitelik, genişletmek istediğiniz düğümünün türü dizesi tanımlayıcısını belirtir.  
  
     Visual Studio tarafından sağlanan yerleşik düğüm türlerini belirtmek için aşağıdaki numaralandırma değerlerinden biri özniteliği oluşturucuya geçirin:  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeTypes>: Site bağlantı düğümleri (site URL'leri görüntüleme düğümler) belirtmek için bu değerleri site düğümleri veya diğer tüm üst düğümler kullanım **Sunucu Gezgini**.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.ExtensionNodeTypes>: Bir SharePoint sitesinde bir listesi, alan veya içerik türünü temsil eden bir düğüm gibi tek tek bir bileşen temsil eden yerleşik düğümleri birini belirtmek için bu değerleri kullanın.  
  
6.  Uygulamanızda <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension.Initialize%2A> yöntemi, kullanım üyeleri *nodeType* düğüme özellikleri eklemek için parametre. Bu parametre bir <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeType> tanımlanan olayları erişimi sağlayan nesne <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents> arabirimi. Örneğin, aşağıdaki olaylar işleyebilir:  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents.NodeChildrenRequested>: Düğüm için yeni alt düğümleri eklemek için bu olayı işleyin. Daha fazla bilgi için bkz: [nasıl yapılır: Sunucu Gezginine özel bir SharePoint düğümü ekleme](../sharepoint/how-to-add-a-custom-sharepoint-node-to-server-explorer.md).  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents.NodeMenuItemsRequested>: Bir özel kısayol menü öğesi için düğüm eklemek için bu olayı işleyin.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents.NodePropertiesRequested>: Özel özellikler düğüme eklemek için bu olayı işleyin. Özellikleri görünür **özellikleri** düğümü seçildiğinde penceresi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde düğümü uzantıların iki farklı türlerinin nasıl oluşturulacağı gösterilmektedir:  
  
-   Bir bağlam menüsü öğesini SharePoint sitesi düğüm ekler uzantı. Menü öğesi tıklattığınızda tıklandığını düğümün adını görüntüler.  
  
-   Adlı özel bir özellik ekler uzantı **ContosoExampleProperty** adlı bir alanı temsil eden her düğüm için **gövde**.  
  
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#9](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorerextension.cs#9)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#9](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorerextension.vb#9)]  
  
 Bu uzantıyı düğümlerine düzenlenebilir dize özelliği ekler. SharePoint sunucusu salt okunur verileri görüntülemek özel özellikler de oluşturabilirsiniz. Bunun nasıl yapılacağını gösteren bir örnek için bkz: [izlenecek yol: web bölümlerini görüntülemek için Sunucu Gezgini genişletmek](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md).  
  
## <a name="compile-the-code"></a>Kod derleme  
 Bu örnekte aşağıdaki derlemelere başvuruları gerektirir:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   Microsoft.VisualStudio.SharePoint.Explorer.Extensions  
  
-   System.ComponentModel.Composition  
  
-   System.Windows.Forms  
  
## <a name="deploy-the-extension"></a>Uzantısı dağıtma  
 Dağıtmak için **Sunucu Gezgini** uzantısı oluşturma bir [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] uzantısı (VSIX) paketini derleme ve uzantısıyla dağıtmak istediğiniz diğer dosyalar için. Daha fazla bilgi için bkz: [Visual Studio'da SharePoint araçları için Uzantılar dağıtmak](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca bkz.
 [Nasıl yapılır: Sunucu Gezginine özel bir SharePoint düğümü ekleme](../sharepoint/how-to-add-a-custom-sharepoint-node-to-server-explorer.md)   
 [Sunucu Gezgininde SharePoint bağlantıları düğümünü genişletme](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [İzlenecek yol: Web bölümlerini görüntülemek için Sunucu Gezgini genişletme](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)   
 [SharePoint araç uzantıları ile özel verileri ilişkilendirme](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)  
  
