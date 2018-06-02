---
title: SharePoint ile özel verileri ilişkilendirme uzantıları araçları | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- projects [SharePoint development in Visual Studio], associating custom data
- project items [SharePoint development in Visual Studio], associating custom data
- SharePoint project items, associating custom data
- SharePoint projects, associating custom data
- SharePoint development in Visual Studio, extensibility features
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0507fe16dd910fe61c4816594125b690c350a1a6
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34691376"
---
# <a name="associating-custom-data-with-sharepoint-tools-extensions"></a>SharePoint araç uzantıları ile özel verileri ilişkilendirme
  SharePoint araç uzantıları belirli nesneleri özel veri ekleyebilirsiniz. Bu, verileri daha sonra diğer koddan uzantınızı erişmek istediğiniz uzantınızı bir parçası olduğunda yararlıdır. Depolamak ve verilere erişmek için özel bir şekilde uygulamak yerine, verileri olan bir nesne uzantı ilişkilendirin ve ardından aynı nesneden daha sonra verileri.  
  
 Visual Studio'da belirli bir öğesiyle ilgili olan verileri korumak istediğiniz özel veri nesne eklemeyi de yararlıdır. SharePoint araç uzantıları yalnızca Visual Studio'da, bu nedenle uzantınızı birkaç farklı öğeleriyle çalışma bir kez yüklenir (projeleri gibi öğeler, proje veya **Sunucu Gezgini** düğümleri) herhangi bir zamanda. Yalnızca belirli bir öğe için ilgili özel veri varsa, bu öğeyi temsil eden nesne verileri ekleyebilirsiniz.  
  
 SharePoint araç uzantıları nesneleri için özel veri eklediğinizde, veri kalmaz. Veriler yalnızca nesne kullanım ömrü sırasında kullanılabilir. Nesne atık toplama tarafından iadesi sonra veriler kaybolur.  
  
 SharePoint Proje sisteminin uzantılarında uzantı kaldırılır sonra devam ederse dize verilerini da kaydedebilirsiniz. Daha fazla bilgi için bkz: [SharePoint Proje sisteminin uzantılarında veri kaydetme](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md).  
  
## <a name="objects-that-can-contain-custom-data"></a>Özel veri içerebilen nesneleri
 Özel veri uygulayan SharePoint araçları nesne modelinde herhangi bir nesne ekleyebileceğiniz <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject> arabirimi. Bu arabirim yalnızca bir özelliğini tanımlar <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A>, özel veri nesneleri koleksiyonu. Aşağıdaki türleri uygulayan <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject>:  
  
-   <xref:Microsoft.VisualStudio.SharePoint.IMappedFolder>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.IMenuItem>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeature>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeatureResourceFile>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFile>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectMember>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectPackage>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentContext>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeType>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeDefinition>  
  
## <a name="add-and-retrieve-custom-data"></a>Ekleme ve özel veri alma
 Bir nesne bir SharePoint araçları uzantısı'nda özel veri eklemek için alma <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> verileri ekleyin ve ardından kullanmak istediğiniz nesnesinin özelliğini <xref:Microsoft.VisualStudio.SharePoint.IAnnotationDictionary.Add%2A> nesnesine verileri eklemek için yöntem.  
  
 Bir SharePoint araçları uzantısı'nda bir nesneden özel veri almak için get <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> nesne ve ardından kullanın aşağıdaki yöntemlerden birini özelliği:  
  
-   <xref:Microsoft.VisualStudio.SharePoint.IAnnotationDictionary.TryGetValue%2A>. Bu yöntem **true** veri nesnesi varsa veya **false** henüz yoksa. Değer türleri veya başvuru türleri örneklerini almak için bu yöntemi kullanabilirsiniz.  
  
-   <xref:Microsoft.VisualStudio.SharePoint.IAnnotationDictionary.GetValue%2A>. Bu yöntem verileri döndürür, bulunup bulunmadığını nesne veya **null** henüz yoksa. Yalnızca başvuru türleri örneklerini almak için bu yöntemi kullanabilirsiniz.  
  
 Aşağıdaki kod örneğinde, belirli bir veri nesnesi zaten bir proje öğesi ile ilişkili olup olmadığını belirler. Veri nesnesi zaten proje öğesi ile ilişkili değil sonra kod nesnesine ekler <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> proje öğesi özelliği. Daha büyük bir örneğin bağlamında bu örnek için bkz [nasıl yapılır: bir özel SharePoint Proje öğe türüne özellik ekleme](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md).  
  
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#13](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemtypeproperty.vb#13)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#13](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemtypeproperty.cs#13)]  
  
## <a name="see-also"></a>Ayrıca bkz.
 [SharePoint araç uzantıları için programlama kavramları ve Özellikler](../sharepoint/programming-concepts-and-features-for-sharepoint-tools-extensions.md)   
 [İzlenecek yol: bir öğe şablonu, bölüm 1 ile bir özel eylem proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [İzlenecek yol: Web bölümlerini görüntülemek için Sunucu Gezgini genişletme](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)   
 [Nasıl yapılır: SharePoint projelerine özellik ekleme](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)   
 [Nasıl yapılır: özel SharePoint Proje öğe türüne özellik ekleme] (.. /SharePoint/How-to-add-a-property-to-a-Custom-SharePoint-Project-item-Type.MD   
 