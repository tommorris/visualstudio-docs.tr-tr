---
title: Hizmetleri kullanma ve sağlama | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples [Visual Studio SDK], services
- Visual Studio, services
- services
ms.assetid: c0b415ba-b825-4da0-9faf-8a60a663e302
caps.latest.revision: 42
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: facf0bb9968e3ffbc9a68eb8eee906f300eb1859
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691521"
---
# <a name="using-and-providing-services"></a>Hizmetleri Kullanma ve Sağlama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [kullanma ve sağlama Hizmetleri](https://docs.microsoft.com/visualstudio/extensibility/using-and-providing-services).  
  
Bir sözleşme iki Vspackage'lar arasında olan bir hizmettir. Bir VSPackage'ı kullanmak başka bir VSPackage arabirimleri belirli bir kümesini sunar. Örneğin, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] sunar <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> isteğe bağlı olarak bir Vspackage'e yükleri hizmet. Bu hizmet sağlayan <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> etkinlik günlüğüne yazmak için kullanılan arabirim. Daha fazla bilgi için [nasıl yapılır: etkinlik günlüğü'nün](../extensibility/how-to-use-the-activity-log.md).  
  
 VSPackage'ları, kendi başlarına kullanmanın Hizmetleri sunabilir <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> arabirimi...  
  
 Visual Studio aşağıdaki gibi önemli hizmetler sunar:  
  
|IDE hizmeti|Açıklama|  
|-----------------|-----------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>|Temel işlevleri, VSPackages ve kayıt defteri ile ilgilenen Hizmetleri IDE için erişim sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>|Temel Pencereleme ve araç ve belge pencereleri oluşturma olanağı gibi IDE kullanıcı Arabirimi ile ilgili işlevleri sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>|Projeleri listeleme, yeni projeler oluşturmak ve proje değişiklikleri izleme özelliği gibi temel çözümü ile ilgili işlevleri sağlar.|  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Hizmet Temel Bileşenleri](../extensibility/internals/service-essentials.md)  
 Visual Studio hizmeti önemli öğelerini gösterir.  
  
 [Nasıl Yapılır: Hizmet Alma](../extensibility/how-to-get-a-service.md)  
 İstek anlatılmaktadır (kullanabilir) bir hizmet.  
  
 [Nasıl Yapılır: Hizmet Sağlama](../extensibility/how-to-provide-a-service.md)  
 Bir hizmetin nasıl ele alınmaktadır.  
  
 [Nasıl Yapılır: Zaman Uyumsuz Visual Studio Hizmeti Sağlama](../extensibility/how-to-provide-an-asynchronous-visual-studio-service.md)  
 Zaman uyumsuz bir hizmetin nasıl ele alınmaktadır.  
  
 [Nasıl Yapılır: Hizmetlerde Sorun Giderme](../extensibility/how-to-troubleshoot-services.md)  
 Ortak sorunları açıklar ve bunların çözümleri sunar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)

