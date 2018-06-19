---
title: Kesme modunda atlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- break mode, stepping
- stepping, in break mode
- debugging [Debugging SDK], stepping in break mode
ms.assetid: b08dc8ee-6c63-4462-a097-6f525cfbb35a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1cf10254ec4642bd6dd671124d4a0600794de6fb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31130391"
---
# <a name="stepping-in-break-mode"></a>Kesme modunda Adımlama
Hata ayıklayıcı kesme modunda olduğunda ve kod üzerinden adım gerekir gerçekleşen işlem açıklanmaktadır:  
  
## <a name="stepping-process"></a>İşlem Adımlama  
  
1.  Çağrı [IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md) ile [STEPKIND](../../extensibility/debugger/reference/stepkind.md) ve [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) bir adım yürütmek için bağımsız değişkenler.  
  
2.  Adım tamamlandığında, gönderme bir [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) durdurma olayı olarak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklayıcısı Olaylarını Çağırma](../../extensibility/debugger/calling-debugger-events.md)