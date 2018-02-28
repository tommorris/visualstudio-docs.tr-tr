---
title: "Geri alma ve eski API kullanarak yineleme yönetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - undo management
ms.assetid: 838c0ddf-fdf3-4df1-8d21-79610b8ba0b1
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c50316b7d5786b1fb3f07255eaf4d875f7f41e5b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="managing-undo-and-redo-by-using-the-legacy-api"></a>Yönetme Geri Al ve eski API'yi kullanarak Yinele
Düzenleyiciler kodu değiştirdiğinizde son değişikliklerini ters kullanıcıların izin geri alma işlemleri desteklemesi gerekir. Çoğu düzenleyicileri altında uygulanan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] otomatik olarak tümleşik geliştirme ortamı (IDE) tarafından sağlanan geri alma desteği olabilir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Nasıl yapılır: uygulama geri alma yönetimi](../extensibility/how-to-implement-undo-management.md)  
 Geri alma özelliği, tek veya birden çok görünüm için düzenleyicileri sağlar.  
  
 [Nasıl yapılır: geri alma yığını temizleyin](../extensibility/how-to-clear-the-undo-stack.md)  
 Bir geri alma yığını temizlemek açıklar.  
  
 [Nasıl yapılır: bağlantılı geri alma Yönetimi'ni kullanın](../extensibility/how-to-use-linked-undo-management.md)  
 Bağlantılı geri alma Yönetimi Düzenleyicisi'ne bir araya getirir.  
  
## <a name="reference"></a>Başvuru  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager>  
 Birden çok görünüm destekleyen bir düzenleyici için geri alma yönetimi sağlar.  
  
## <a name="related-sections"></a>İlgili Bölümler