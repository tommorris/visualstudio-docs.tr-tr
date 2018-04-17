---
title: SharePoint Proje sistem türleri ve diğer Visual Studio Proje türleri arasında dönüştürme | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project service
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6cf039f3d5330b2f4869ae323ac358a1220c2fbf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types"></a>SharePoint Proje Sistem Türleri ve Diğer Visual Studio Proje Türleri Arasında Dönüştürme
  Bazı durumlarda SharePoint Proje sistemi nesnenin olabilir ve Visual Studio Otomasyon nesne modeli veya tümleştirme nesne modeli, karşılık gelen bir nesne özelliklerini kullanmak istediğiniz veya tam tersi. Bu durumlarda, kullandığınız <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> farklı nesne modeline nesneyi dönüştürmek için SharePoint Proje hizmeti yöntemi.  
  
 Örneğin, sahip olabileceğiniz bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> nesnesi, ancak yalnızca kullanılabilir yöntemleri kullanmak istediğiniz bir <xref:EnvDTE.Project> veya <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject> nesnesi. Bu durumda, kullanabileceğiniz <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> dönüştürmek için yöntem <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> için bir <xref:EnvDTE.Project> veya <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject>.  
  
 Visual Studio Otomasyon nesne modeli ve Visual Studio tümleştirmesi nesne modeli hakkında daha fazla bilgi için bkz: [programlama modeli, SharePoint araç uzantıları genel bakış](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md).  
  
## <a name="types-of-conversions"></a>Tür dönüştürmeleri  
 Aşağıdaki tabloda, bu yöntem SharePoint Proje sisteminin ve diğer Visual Studio nesne modelleri arasında dönüştürme türleri listelenmektedir.  
  
|SharePoint Proje sistem türü|Karşılık gelen türlerinde Otomasyonu ve tümleştirme nesne modelleri|  
|------------------------------------|-------------------------------------------------------------------------|  
|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProject>|<xref:EnvDTE.Project><br /><br /> veya<br /><br /> Herhangi bir arabirimi projesi için temel alınan COM nesnesi tarafından uygulanan Visual Studio tümleştirmesi nesne modeli. Bu arabirimleri dahil <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>, <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject> (veya türetilmiş bir arabirim) ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage>. Projeler tarafından uygulanan ana arabirimleri listesi için bkz: [proje modeli çekirdek bileşenleri](/visualstudio/extensibility/internals/project-model-core-components).|  
|<xref:Microsoft.VisualStudio.SharePoint.IMappedFolder><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFile><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeature><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeatureResourceFile><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectPackage>|<xref:EnvDTE.ProjectItem><br /><br /> veya<br /><br /> A<xref:System.UInt32> proje üye tanımlar (bir VSITEMID olarak da bilinir) değeri <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> , içerir. Bu değer için geçirilebilir *ItemId* bazı parametresinin <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> yöntemleri.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde nasıl kullanılacağı ortaya <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> dönüştürmek için yöntem bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> nesnesine bir <xref:EnvDTE.Project>.  
  
 [!code-csharp[SPExtensibility.ProjectService.FromDTE#2](../sharepoint/codesnippet/CSharp/spprojectserviceaddin/connect.cs#2)]
 [!code-vb[SPExtensibility.ProjectService.FromDTE#2](../sharepoint/codesnippet/VisualBasic/spprojectserviceaddin/connect.vb#2)]  
  
 Bu örnek gerektirir:  
  
-   Uzantı SharePoint Proje sisteminin EnvDTE.dll derlemesine başvuru içeriyor. Daha fazla bilgi için bkz: [SharePoint Proje sistemini genişletme](../sharepoint/extending-the-sharepoint-project-system.md).  
  
-   Kaydeder kod `projectService_ProjectAdded` yöntemini <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectAdded> olayı bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> nesnesi. Bir örnek için bkz: [nasıl yapılır: bir SharePoint proje uzantısı oluşturma](../sharepoint/how-to-create-a-sharepoint-project-extension.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Proje hizmetini kullanma](../sharepoint/using-the-sharepoint-project-service.md)   
 [Nasıl yapılır: SharePoint Proje hizmetini alma](../sharepoint/how-to-retrieve-the-sharepoint-project-service.md)   
 [SharePoint Araç Uzantılarının Programlama Modeline Genel Bakış](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)  
  
  