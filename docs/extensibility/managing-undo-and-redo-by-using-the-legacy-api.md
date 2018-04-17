---
title: Geri alma ve eski API kullanarak yineleme yönetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - undo management
ms.assetid: 838c0ddf-fdf3-4df1-8d21-79610b8ba0b1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 93bb65fa9865c5ca7386925d2c145f2acbc0993a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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