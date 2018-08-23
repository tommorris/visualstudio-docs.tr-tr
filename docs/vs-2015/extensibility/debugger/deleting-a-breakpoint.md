---
title: Kesme noktasını silme | Microsoft Docs
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
- breakpoints, deleting
- debugging [Debugging SDK], deleting breakpoints
ms.assetid: 75a046cc-d20a-4c79-ad2d-1f18426ac5d0
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 18b88cc55a4c641e56c062356a9f74c2224835a8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686383"
---
# <a name="deleting-a-breakpoint"></a>Kesme Noktasını Silme
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [kesme noktasını silme](https://docs.microsoft.com/visualstudio/extensibility/debugger/deleting-a-breakpoint).  
  
Aşağıdaki bir bekleyen kesme noktasının silerken işlemi açıklanmaktadır:  
  
## <a name="deletion-process"></a>Silme işlemi  
 Oturum hata ayıklama Yöneticisi (SDM) çağıran [IDebugPendingBreakpoint2::Delete](../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md) ondan bağlı bekleyen kesme noktasının ve ilişkili tüm kesme noktalarını kaldırmak için yöntemi.  
  
> [!NOTE]
>  Tek bir bağlı Kesme noktasının bir çağrı tarafından da silinebilir [IDebugBoundBreakpoint2::Delete](../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklayıcısı Olaylarını Çağırma](../../extensibility/debugger/calling-debugger-events.md)

