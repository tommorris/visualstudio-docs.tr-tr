---
title: Sunucu Gezgininde SharePoint bağlantıları düğümünü genişletme | Microsoft Docs
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
- SharePoint Connections [SharePoint development in Visual Studio], creating a new node type
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0eabca43f604d92ecab78dccae281a450f7c0400
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="extending-the-sharepoint-connections-node-in-server-explorer"></a>Sunucu Gezgininde SharePoint Bağlantılarını Genişletme
  Visual Studio'da geliştirme bilgisayarındaki yerel SharePoint siteleri kullanarak bağlanabilirsiniz **SharePoint bağlantıları** düğümünde**Sunucu Gezgini** penceresi. Bu düğüm bileşenlerin yerel SharePoint sitelerinin çoğu bir hiyerarşik ağaç görünümünde görüntüler. Örneğin, yerel sitelerinde listeler, belge kitaplıkları ve içerik türlerini görüntüleyebilirsiniz. Kullanma hakkında daha fazla bilgi için **Sunucu Gezgini** yerel SharePoint sitelerine bağlanmak için bkz: [SharePoint bağlantıları kullanarak Sunucu Gezgini gözatma](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md).  
  
 Genişletebilirsiniz **SharePoint bağlantıları** düğüm varolan düğümleri için Uzantılar oluşturarak veya özel düğüm türü oluşturma ve düğümler hiyerarşisini ekleme.  
  
## <a name="tasks-for-extending-the-sharepoint-connections-node"></a>SharePoint bağlantıları düğümünü genişletme için görevler  
 Varolan bir düğümü genişletmek için uygulayan bir Visual Studio uzantısı oluşturma <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> arabirimi. Bir düğüm genişlettiğinizde, kendi kısayol menüsü öğelerini veya özel özellikler gibi düğüme işlevselliği ekleyebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Sunucu Gezgininde SharePoint düğümünü genişletme](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md).  
  
 Özel düğüm türü oluşturmak için uygulayan bir Visual Studio uzantısı oluşturun <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> arabirimi. Görüntülenmeyen SharePoint siteleri bileşenlerinin görüntülemek istiyorsanız, özel bir düğüm oluşturabilirsiniz **Sunucu Gezgini** varsayılan olarak. Örneğin, **Sunucu Gezgini** bu özel bir düğüme varsayılan, ancak bir SharePoint sitesinin Web Bölümü Galerisi ekleyebilirsiniz görüntüleme yapar. Daha fazla bilgi için bkz: [nasıl yapılır: Sunucu Gezginine özel bir SharePoint düğümü ekleme](../sharepoint/how-to-add-a-custom-sharepoint-node-to-server-explorer.md) ve [izlenecek yol: Görüntü Web bölümleri için Sunucu Gezgini genişletme](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md).  
  
## <a name="adding-custom-properties-to-nodes"></a>Düğümlerine özel özellikler ekleme  
 Bir düğümü genişletmek veya bir özel düğüm türü oluşturduğunuzda, düğüme özel özellikleri ekleyebilirsiniz. Özellikleri görünür **özellikleri** düğümü seçildiğinde penceresi.  
  
 Bir düğüm eklemek özel özellikler iki tür vardır:  
  
-   Bir SharePoint sitesinden salt okunur veri kümesi görüntülemek özelliklerini. Veri düğümü temsil eder SharePoint bileşenini açıklar. Bunun nasıl yapılacağı izlenecek yol için bkz: [izlenecek yol: Görüntü Web bölümleri için Sunucu Gezgini genişletme](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md).  
  
-   Özel okuma/yazma veri görüntülemek özelliklerini. Bunun nasıl yapılacağını gösteren bir kod örneği için bkz: [nasıl yapılır: Sunucu Gezgininde SharePoint düğümünü genişletme](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md).  
  
## <a name="getting-data-for-built-in-nodes"></a>Yerleşik düğümleri için veri alma  
 Visual Studio tarafından sağlanan yerleşik düğümlerinin tümü temsil ettikleri SharePoint bileşenle ilgili bazı verileri içerir. Örneğin, SharePoint sitesindeki bir listesini temsil eden bir düğüm başlığı ve liste için varsayılan görünüm URL'sini gibi listesi hakkında bazı verileri sağlar.  
  
 Bu verilere erişmek için bir veri nesnesinden almak <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> özelliği <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode> ilgilendiğiniz düğümünü temsil eden nesne. Veri nesnesi türü düğüm türüne bağlıdır.  
  
 Aşağıdaki kod örneğinde veri nesnesi için bir liste düğümü alma gösterilmektedir. Daha büyük bir örneğin bağlamında bu örnek için bkz [nasıl yapılır: Sunucu Gezgininde yerleşik bir SharePoint düğümü için Veri Al](../sharepoint/how-to-get-data-for-a-built-in-sharepoint-node-in-server-explorer.md).  
  
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#11](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorerextensionnodeinfo.vb#11)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#11](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorerextensionnodeinfo.cs#11)]  
  
 Aşağıdaki tabloda her yerleşik düğüm türü için veri nesne türlerini listeler.  
  
|Düğüm türü|Veri nesnesi türü|  
|---------------|----------------------|  
|SharePoint sitesi düğümü|<xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerSiteNodeInfo>|  
|İçerik türü|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IContentTypeNodeInfo>|  
|Özellik|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IFeatureNodeInfo>|  
|Alan|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IFieldNodeInfo>|  
|List|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IListNodeInfo>|  
|Liste şablonu|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IListTemplateNodeInfo>|  
|Liste Görünümü (Microsoft.SharePoint.SPView)|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IListViewNodeInfo>|  
|İş akışı ilişkilendirme|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IWorkflowAssociationNodeInfo>|  
|İş akışı şablonu|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IWorkflowTemplateNodeInfo>|  
  
 Kullanma hakkında daha fazla bilgi için <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> özelliği, bkz: [SharePoint araç uzantıları ile özel verileri ilişkilendirme](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Web bölümlerini görüntülemek için Sunucu Gezgini genişletme](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)   
 [Nasıl yapılır: Sunucu Gezgininde SharePoint düğümünü genişletme](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)   
 [Nasıl yapılır: Sunucu Gezginine özel bir SharePoint düğümü ekleme](../sharepoint/how-to-add-a-custom-sharepoint-node-to-server-explorer.md)   
 [Nasıl yapılır: Sunucu Gezgininde yerleşik bir SharePoint düğümü için veri alma](../sharepoint/how-to-get-data-for-a-built-in-sharepoint-node-in-server-explorer.md)   
 [SharePoint araç uzantıları ile özel verileri ilişkilendirme](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)   
 [Sunucu Gezgini kullanarak SharePoint bağlantılarına gözatma](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)   
 [SharePoint Araçlarını Visual Studio'da Genişletme](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)  
  
  