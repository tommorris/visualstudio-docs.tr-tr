---
title: "Kullanarak ve hizmetleri sağlayan | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples [Visual Studio SDK], services
- Visual Studio, services
- services
ms.assetid: c0b415ba-b825-4da0-9faf-8a60a663e302
caps.latest.revision: "41"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e28b66dea8440c969926abd3892739f4e041b064
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="using-and-providing-services"></a>Kullanarak ve hizmetleri sağlar
İki VSPackages arasında bir sözleşme hizmetidir. Bir VSPackage arabirimleri kullanmak üzere başka bir VSPackage için belirli bir dizi sunar. Örneğin, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sunar <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> isteğe bağlı olarak tüm VSPackage yükleri hizmet. Bu hizmet sağlayan <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> etkinlik günlüğü yazmak için kullanılan arabirim. Daha fazla bilgi için bkz: [nasıl yapılır: etkinlik günlüğü kullanın](../extensibility/how-to-use-the-activity-log.md).  
  
 VSPackages tarafından kendi kullanmanın Hizmetleri sunabilir <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> arabirimi...  
  
 Visual Studio aşağıdaki gibi önemli hizmetler sunar:  
  
|IDE hizmeti|Açıklama|  
|-----------------|-----------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>|Temel işlevleri, VSPackages ve kayıt defteri ile ilgilenen IDE erişim hizmetleri sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>|Temel Pencereleme ve araçları ve belge pencereleri oluşturma yeteneği gibi IDE UI ilgili işlevleri sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>|Projeleri listeleme, yeni projeler oluşturun ve proje değişiklikleri izleme yeteneğini gibi temel çözüm ilgili işlevleri sağlar.|  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Hizmet temelleri](../extensibility/internals/service-essentials.md)  
 Visual Studio hizmet önemli öğelerini gösterir.  
  
 [Nasıl yapılır: bir hizmeti Al](../extensibility/how-to-get-a-service.md)  
 İstek açıklanmaktadır (kullanabilir) bir hizmet.  
  
 [Nasıl yapılır: bir hizmet sağlar](../extensibility/how-to-provide-a-service.md)  
 Bir hizmet sağlamak nasıl ele alınmaktadır.  
  
 [Nasıl yapılır: bir zaman uyumsuz Visual Studio hizmet sağlayın](../extensibility/how-to-provide-an-asynchronous-visual-studio-service.md)  
 Zaman uyumsuz bir hizmet sağlamak üzere nasıl ele alınmaktadır.  
  
 [Nasıl yapılır: Hizmetleri sorunlarını giderme](../extensibility/how-to-troubleshoot-services.md)  
 Sık karşılaşılan sorunlar anlatılmaktadır ve bunların çözümleri sunar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)