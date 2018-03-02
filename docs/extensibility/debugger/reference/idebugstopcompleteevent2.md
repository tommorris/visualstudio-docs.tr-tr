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
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: aa8941decfb4e64906c57b719df711ce8779df9c
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2018
---
# <a name="idebugstopcompleteevent2"></a>IDebugStopCompleteEvent2

Bir programı durdurulduğunda hata ayıklama altyapısı (DE) oturum hata ayıklama Yöneticisi (SDM) Bu isteğe bağlı bir olay gönderebilir.

## <a name="syntax"></a>Sözdizimi

```
IDebugStopCompleteEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar

Bu arabirim, Visual Studio 2005 ile sunulmuştur. Önceki sürümlerde, zaman uyumsuz durdurma desteklememektedir.

[Durdur](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) birden çok işlem ya da çok program senaryolarda SDM tarafından çağrılır. Bir program SDM durdurma olay gönderdiğinde, SDM çok durdurmak için diğer programları ister.

Durma zaman uyumsuz olarak bir programı durdurdu SDM bildirmek için kullanılır. SDM yorumlayıcı hata ayıklama altyapının için yararlıdır bildiren, bazen kod hata ayıklaması içinde çalıştığı program, bunu [durdurmak](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) zaman uyumlu olarak tamamlanamıyor. Hata ayıklama altyapısı bu zaman uyumsuz bildirim uygulamadığınız isteyip istemediğini, döndürmesi gerekir `S_ASYNC_STOP` gelen [durdurmak](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md).

## <a name="requirements"></a>Gereksinimler

Başlık: msdbg.h

Namespace: Microsoft.VisualStudio.Debugger.Interop

Derleme: Microsoft.VisualStudio.Debugger.Interop.dll