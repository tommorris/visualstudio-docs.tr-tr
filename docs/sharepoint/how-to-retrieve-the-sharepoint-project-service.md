---
title: "Nasıl yapılır: SharePoint Proje hizmetini alma | Microsoft Docs"
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
helpviewer_keywords: SharePoint project service
ms.assetid: 3d8b7adf-2603-4247-9b61-6326a1dd0dec
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b5ecc739da7cc3aa78a5c175ae323f5cd2447d40
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-retrieve-the-sharepoint-project-service"></a>Nasıl yapılır: SharePoint Proje Hizmetini Alma
  SharePoint Proje hizmeti çözümleri aşağıdaki türden erişebilirsiniz:  
  
-   SharePoint Proje sisteminin proje uzantısı, proje öğe uzantısına veya proje öğesi türü tanımı gibi uzantısı. Bu tür uzantıları hakkında daha fazla bilgi için bkz: [SharePoint Proje sistemini genişletme](../sharepoint/extending-the-sharepoint-project-system.md).  
  
-   Bir uzantısı olarak **SharePoint bağlantıları** düğümünde **Sunucu Gezgini**. Bu tür uzantıları hakkında daha fazla bilgi için bkz: [Sunucu Gezgininde SharePoint bağlantıları düğümünü genişletme](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md).  
  
-   Visual Studio uzantısı, bir VSPackage gibi başka bir tür.  
  
## <a name="retrieving-the-service-in-project-system-extensions"></a>Proje sisteminin uzantılarında hizmet alınıyor  
 SharePoint Proje sisteminin herhangi uzantısında kullanarak proje hizmeti erişebilirsiniz <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.ProjectService%2A> özelliği bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> nesnesi.  
  
 Aşağıdaki yordamları kullanarak proje hizmetini de alabilirsiniz.  
  
#### <a name="to-retrieve-the-service-in-a-project-extension"></a>Bir proje uzantısı hizmetinde almak için  
  
1.  Uygulamanızda <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> arabirim, bulun <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension.Initialize%2A> yöntemi.  
  
2.  Kullanım *projectService* hizmete erişmek için parametre.  
  
     Aşağıdaki kod örneğinde proje hizmeti ileti yazmak için nasıl kullanılacağı gösterilmektedir **çıkış** penceresi ve **hata listesi** Basit Proje uzantısı penceresinde.  
  
     [!code-vb[SPExtensibility.ProjectService.FromProjectSystemExtensions#1](../sharepoint/codesnippet/VisualBasic/spextensibility.projectservice.fromprojectsystemextensions.getprojectservice/extension/extension.vb#1)]
     [!code-csharp[SPExtensibility.ProjectService.FromProjectSystemExtensions#1](../sharepoint/codesnippet/CSharp/spextensibility.projectservice.fromprojectsystemextensions.getprojectservice/extension/extension.cs#1)]  
  
     Proje uzantıları oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint proje uzantısı oluşturma](../sharepoint/how-to-create-a-sharepoint-project-extension.md).  
  
#### <a name="to-retrieve-the-service-in-a-project-item-extension"></a>Bir proje öğesi uzantısı hizmetinde almak için  
  
1.  Uygulamanızda <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> arabirim, bulun <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> yöntemi.  
  
2.  Kullanım <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType.ProjectService%2A> özelliği *projectItemType* parametresi hizmeti alınamadı.  
  
     Aşağıdaki kod örneğinde proje hizmeti ileti yazmak için nasıl kullanılacağı gösterilmektedir **çıkış** penceresi ve **hata listesi** basit bir uzantısı penceresinde **listesi tanımını** proje öğesi.  
  
     [!code-vb[SPExtensibility.ProjectService.FromProjectSystemExtensions#2](../sharepoint/codesnippet/VisualBasic/spextensibility.projectservice.fromprojectsystemextensions.getprojectservice/extension/extension.vb#2)]
     [!code-csharp[SPExtensibility.ProjectService.FromProjectSystemExtensions#2](../sharepoint/codesnippet/CSharp/spextensibility.projectservice.fromprojectsystemextensions.getprojectservice/extension/extension.cs#2)]  
  
     Proje öğesi uzantıları oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint proje öğesi uzantısı oluşturma](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md).  
  
#### <a name="to-retrieve-the-service-in-a-project-item-type-definition"></a>Bir proje öğesi türü tanımını hizmetinde almak için  
  
1.  Uygulamanızda <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> arabirim, bulun <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> yöntemi.  
  
2.  Kullanım <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.ProjectService%2A> özelliği *typeDefinition* parametresi hizmeti alınamadı.  
  
     Aşağıdaki kod örneğinde proje hizmeti ileti yazmak için nasıl kullanılacağı gösterilmektedir **çıkış** penceresi ve **hata listesi** Basit Proje öğesi türü tanımı penceresinde.  
  
     [!code-vb[SPExtensibility.ProjectService.FromProjectSystemExtensions#3](../sharepoint/codesnippet/VisualBasic/spextensibility.projectservice.fromprojectsystemextensions.getprojectservice/extension/extension.vb#3)]
     [!code-csharp[SPExtensibility.ProjectService.FromProjectSystemExtensions#3](../sharepoint/codesnippet/CSharp/spextensibility.projectservice.fromprojectsystemextensions.getprojectservice/extension/extension.cs#3)]  
  
     Proje öğesi türlerini tanımlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint proje öğesi türü tanımlama](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).  
  
## <a name="retrieving-the-service-in-server-explorer-extensions"></a>Sunucu Gezgini uzantıları hizmetinde alınıyor  
 Bir uzantısına **SharePoint bağlantıları** düğümünde **Sunucu Gezgini**, proje hizmetini kullanarak erişebilirsiniz <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode.ServiceProvider%2A> özelliği bir <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode> nesnesi.  
  
#### <a name="to-retrieve-the-service-in-a-server-explorer-extension"></a>Bir sunucu Gezgini uzantısında hizmeti alınamadı  
  
1.  Alma bir <xref:System.IServiceProvider> nesnesinin <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode.ServiceProvider%2A> özelliği bir <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode> uzantınızı nesne.  
  
2.  Kullanım <xref:System.IServiceProvider.GetService%2A> istemek için yöntemi bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> nesnesi.  
  
     Aşağıdaki kod örneğinde proje hizmeti ileti yazmak için nasıl kullanılacağı gösterilmektedir **çıkış** penceresi ve **hata listesi** listesidüğümleruzantıekleyenbirkısayolmenüsüpenceresinden**Sunucu Gezgini**.  
  
     [!code-vb[SPExtensibility.ProjectService.FromSPExplorerExtensions#1](../sharepoint/codesnippet/VisualBasic/spextensibility.projectservice.fromspexplorerextensions.getprojectservice/extension/extension.vb#1)]
     [!code-csharp[SPExtensibility.ProjectService.FromSPExplorerExtensions#1](../sharepoint/codesnippet/CSharp/spextensibility.projectservice.fromspexplorerextensions.getprojectservice/extension/extension.cs#1)]  
  
     Genişletme hakkında daha fazla bilgi için **SharePoint bağlantıları** düğümünde **Sunucu Gezgini**, bkz: [nasıl yapılır: Sunucu Gezgininde SharePoint düğümünü genişletme](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md).  
  
## <a name="retrieving-the-service-in-other-visual-studio-extensions"></a>Diğer Visual Studio uzantıları hizmetinde alınıyor  
 Bir VSPackage ya da erişimi olan herhangi bir Visual Studio uzantı proje hizmetini alma bir <xref:EnvDTE80.DTE2> Otomasyon nesne modelinde uygulayan bir proje şablonu Sihirbazı gibi <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> arabirimi.  
  
 Bir VSPackage talep edebilir bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> aşağıdaki yöntemlerden birini kullanarak nesnesi:  
  
-   <xref:System.IServiceProvider.GetService%2A> Türeyen bir yönetilen VSPackage yöntemi <xref:Microsoft.VisualStudio.Shell.Package> sınıfı. Daha fazla bilgi için bkz: [nasıl yapılır: bir hizmet elde](../extensibility/how-to-get-a-service.md).  
  
-   Statik <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> yöntemi. Daha fazla bilgi için bkz: [kullanım GetGlobalService](../extensibility/internals/service-essentials.md#how-to-use-getglobalservice).  
  
 Erişimi olan bir Visual Studio Uzantısı'nda bir <xref:EnvDTE80.DTE2> nesnesi isteyebileceği bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> kullanarak nesne <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A> yöntemi bir <xref:Microsoft.VisualStudio.Shell.ServiceProvider> nesnesi. Daha fazla bilgi için bkz: [DTE nesneden bir hizmet alma](../extensibility/how-to-get-a-service.md#getting-a-service-from-the-dte-object).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Proje hizmetini kullanma](../sharepoint/using-the-sharepoint-project-service.md)   
 [Nasıl yapılır: bir hizmeti Al](../extensibility/how-to-get-a-service.md)   
 [Nasıl yapılır: sihirbazları proje şablonlarıyla kullanma](../extensibility/how-to-use-wizards-with-project-templates.md)  
  
  