---
title: IDebugStopCompleteEvent2 | Microsoft Docs
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
- IDebugStopCompleteEvent2 interface
ms.assetid: ff3e89f4-61bb-489d-901c-447260100218
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f880888ab675fc7923b50e3b1fbce144f8108abd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694347"
---
# <a name="idebugstopcompleteevent2"></a>IDebugStopCompleteEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugStopCompleteEvent2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugstopcompleteevent2).  
  
Bir program durduğunda, hata ayıklama altyapısı (DE) oturum hata ayıklama Yöneticisi (SDM) Bu isteğe bağlı bir olay gönderebilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugStopCompleteEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Yeni bir arabirimi budur [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]. Önceki sürümlerde, zaman uyumsuz durdurma desteklememektedir.  
  
 [Durdur](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) SDM senaryolarda, çok işlemli veya çok programı tarafından çağrılır. Bir program için SDM durdurma olay gönderdiğinde SDM çok durdurmak için diğer programları ister.  
  
 Zaman uyumsuz olarak bir program durduktan SDM bildirmek için kullanılır. Bazen kod hata ayıklaması yapılan programa içinde çalıştığı, yorumlayıcı hata ayıklama altyapısı için kullanışlıdır şekilde [Durdur](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) zaman uyumlu olarak tamamlanamadı. Hata ayıklama altyapısı bu zaman uyumsuz bildirim görevlendirmek isteyip istemediği, döndürmesi gereken `S_ASYNC_STOP` gelen [Durdur](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md).  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll

