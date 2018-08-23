---
title: Geri alma ve eski API'yi kullanarak yönetme | Microsoft Docs
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
- editors [Visual Studio SDK], legacy - undo management
ms.assetid: 838c0ddf-fdf3-4df1-8d21-79610b8ba0b1
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0bb1cc883941c8365e4d4341c93084beaef44d48
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687958"
---
# <a name="managing-undo-and-redo-by-using-the-legacy-api"></a>Yönetme geri alma ve eski API'yi kullanarak yineleme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [yönetme Geri Al ve Yinele eski API'yi kullanarak](https://docs.microsoft.com/visualstudio/extensibility/managing-undo-and-redo-by-using-the-legacy-api).  
  
Düzenleyiciler, bunlar kod değiştirdiğinizde, son değişikliklerini ters kullanıcıların geri alma işlemlerinin desteklemesi gerekir. Çoğu düzenleyicileri altında uygulanan [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ve [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] otomatik olarak tümleşik geliştirme ortamı (IDE) tarafından sağlanan geri alma desteği sağlayabilirsiniz.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Nasıl yapılır: uygulamak yönetim geri alma](../extensibility/how-to-implement-undo-management.md)  
 Geri alma özelliği, tek veya birden çok görünüm için düzenleyicileri sağlar.  
  
 [Nasıl yapılır: geri alma yığını Temizle](../extensibility/how-to-clear-the-undo-stack.md)  
 Bir geri alma yığını Temizle açıklar.  
  
 [Nasıl yapılır: bağlantılı geri alma Yönetimi'ni kullanın](../extensibility/how-to-use-linked-undo-management.md)  
 Bağlantılı geri alma yönetim, düzenleyicisine içerir.  
  
## <a name="reference"></a>Başvuru  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager>  
 Birden çok görünüm destekleyen bir düzenleyici için geri alma yönetimi sağlar.  
  
## <a name="related-sections"></a>İlgili Bölümler

