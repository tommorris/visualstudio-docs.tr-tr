---
title: SharePoint Proje hizmetini kullanma | Microsoft Docs
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
- SharePoint development in Visual Studio, extensibility features
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2a74f2b7a2810a268c68306490dbbe2c197f0c72
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120422"
---
# <a name="use-the-sharepoint-project-service"></a>SharePoint Proje hizmetini kullanma
  SharePoint Proje sisteminin proje sisteme ilgili görevleri gerçekleştirmek için kullanabileceğiniz bir proje hizmeti içerir. Proje hizmeti bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> nesnesi.  
  
 Tüm SharePoint araçları uzantısında SharePoint Proje hizmeti erişebilir. Visual Studio uzantıları, eklentiler ve VSPackages gibi diğer türleri içinde de erişebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: SharePoint Proje hizmetini alma](../sharepoint/how-to-retrieve-the-sharepoint-project-service.md).  
  
## <a name="project-service-features"></a>Proje hizmet özellikleri
 Aşağıdaki tabloda SharePoint Proje hizmetini kullanarak gerçekleştirebileceğiniz görevler listelenir ve <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> yöntemi veya özelliği her bir görevi gerçekleştirmek için kullanın.  
  
|Görev|Kullanılacak üye|  
|----------|-------------------|  
|Visual Studio'da açık olan herhangi bir SharePoint projeye erişin.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Projects%2A> özellik.|  
|Tüm SharePoint proje öğesi türleri (yerleşik ve özel proje öğesi türleri dahil) kullanılabilir erişebilirsiniz.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.ProjectItemTypes%2A> özellik.|  
|Tüm SharePoint projelerine (yerleşik ve özel dağıtım adımları dahil) kullanılabilir dağıtım adımları erişin.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.DeploymentSteps%2A> özellik.|  
|Bir SharePoint Proje kodda bir geliştirici refactors olduğunda ortaya erişim olayları.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.CodeRefactoringEvents%2A> özellik.|  
|Özel bir yürütme *SharePoint komutu* SharePoint sunucusu nesne modeline çağırır. SharePoint komutları hakkında daha fazla bilgi için bkz: [SharePoint nesne modellerini çağırma](../sharepoint/calling-into-the-sharepoint-object-models.md).|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.SharePointConnection%2A> özellik.|  
|SharePoint Proje sistem Visual Studio Otomasyon nesne modeli veya tümleştirme nesne modeli, bir tür için bir tür dönüştürme ve tersi. Daha fazla bilgi için bkz: [SharePoint Proje sistem türleri ve diğer Visual Studio Proje türleri arasında dönüştürme](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md).|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> yöntem.|  
|İletileri yazma **çıkış** penceresi veya **hata listesi** Visual Studio'daki.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Logger%2A> özellik.|  
|Visual Studio'da kullanılabilir olan diğer hizmetler erişir.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.ServiceProvider%2A> özellik.|  
|Çözüm hata ayıklama için kullanılan yerel SharePoint sitesi yükleme klasörü yolunu alır.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.SharePointInstallPath%2A> özellik.|  
|Belirlemek olup olmadığını [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] veya [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] bilgisayara yüklendi.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.IsSharePointInstalled%2A> özellik.|  
|Bir özellik veya bir SharePoint çözüm paketi doğrulayın.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.PackageValidationProvider%2A> özellik.|  
  
## <a name="see-also"></a>Ayrıca bkz.
 [SharePoint Proje sistem türleri ve diğer Visual Studio Proje türleri arasında dönüştürme](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)   
 [Nasıl yapılır: SharePoint Proje hizmetini alma](../sharepoint/how-to-retrieve-the-sharepoint-project-service.md)   
 [Visual Studio'da SharePoint araçları genişletme](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)   
 [Araç uzantılarının programlama modeline SharePoint genel bakış](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)   
 [Nasıl yapılır: bir hizmet DTE nesnesinden alın](http://msdn.microsoft.com/library/bb166401.aspx)  
  
