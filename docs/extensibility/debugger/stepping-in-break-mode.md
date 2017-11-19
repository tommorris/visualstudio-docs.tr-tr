---
title: Kesme modunda atlama | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- break mode, stepping
- stepping, in break mode
- debugging [Debugging SDK], stepping in break mode
ms.assetid: b08dc8ee-6c63-4462-a097-6f525cfbb35a
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 011de9ce3e4e1445354f907dcf56a0f4ecbef6bc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="stepping-in-break-mode"></a>Kesme modunda Adımlama
Hata ayıklayıcı kesme modunda olduğunda ve kod üzerinden adım gerekir gerçekleşen işlem açıklanmaktadır:  
  
## <a name="stepping-process"></a>İşlem Adımlama  
  
1.  Çağrı [IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md) ile [STEPKIND](../../extensibility/debugger/reference/stepkind.md) ve [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) bir adım yürütmek için bağımsız değişkenler.  
  
2.  Adım tamamlandığında, gönderme bir [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) durdurma olayı olarak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arama hata ayıklayıcı olayları](../../extensibility/debugger/calling-debugger-events.md)