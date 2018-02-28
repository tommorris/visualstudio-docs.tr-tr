---
title: IDebugStopCompleteEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugStopCompleteEvent2 interface
ms.assetid: ff3e89f4-61bb-489d-901c-447260100218
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 5d59de29078db46f716fe9d01a3f3fa076139ddf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugstopcompleteevent2"></a>IDebugStopCompleteEvent2
Bir programı durdurulduğunda hata ayıklama altyapısı (DE) oturum hata ayıklama Yöneticisi (SDM) Bu isteğe bağlı bir olay gönderebilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugStopCompleteEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Yeni bir arabirim için budur [!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)]. Önceki sürümlerde, zaman uyumsuz durdurma desteklememektedir.  
  
 [Durdur](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) birden çok işlem ya da çok program senaryolarda SDM tarafından çağrılır. Bir program SDM durdurma olay gönderdiğinde, SDM çok durdurmak için diğer programları ister.  
  
 Zaman uyumsuz olarak bir programı durdurdu SDM bildirmek için kullanılır. Bu bazen kod hata ayıklaması program içinde çalıştığı, yorumlayıcı hata ayıklama altyapının için yararlıdır şekilde [durdurmak](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) zaman uyumlu olarak tamamlanamıyor. Hata ayıklama altyapısı bu zaman uyumsuz bildirim uygulamadığınız isteyip istemediğini, döndürmesi gerekir `S_ASYNC_STOP` gelen [durdurmak](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md).  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll