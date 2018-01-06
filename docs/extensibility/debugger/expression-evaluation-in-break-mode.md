---
title: "İfade değerlendirme kesme modunda | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- break mode, expression evaluation
- debugging [Debugging SDK], expression evaluation
- expression evaluation, break mode
ms.assetid: 34fe5b58-15d5-4387-a266-72120f90a4b6
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: cd28633fcb4b8186dae154428e489d51041aa8b2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="expression-evaluation-in-break-mode"></a>Kesme modunda ifade değerlendirme
Aşağıdaki hata ayıklayıcı kesme modunda olduğunda ve ifade değerlendirme yürütmeniz gerekir oluşan işlemini açıklar.  
  
## <a name="expression-evaluation-process"></a>İfade değerlendirme işlemi  
 Bir ifade değerlendirme ilgili temel adımlar şunlardır:  
  
1.  Oturum hata ayıklama Yöneticisi'ni (SDM) çağırır [IDebugStackFrame2::GetExpressionContext](../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) bir ifade bağlam arabirimi sağlamak için [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md).  
  
2.  SDM sonra çağırır [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) ayrıştırılacak dizesiyle.  
  
3.  Hatanın nedenini ParseText S_OK döndürmezse döndürülür.  
  
     -Aksi takdirde-  
  
     ParseText S_OK döndürürse SDM sonra ya da çağırabilirsiniz [IDebugExpression2::EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) veya [IDebugExpression2::EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) ayrıştırılmış ifadedeki son değeri elde edilir.  
  
    -   Kullanarak söz konusu olduğunda `IDebugExpression2::EvaluateSync`, verilen geri çağırma arabirimi değerlendirme devam eden işlem iletişim kurmak için kullanılır. Son değer döndürülür bir [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) arabirimi.  
  
    -   Kullanarak söz konusu olduğunda `IDebugExpression2::EvaluateAsync`, verilen geri çağırma arabirimi değerlendirme devam eden işlem iletişim kurmak için kullanılır. Değerlendirme tamamlandıktan sonra EvaluateAsync gönderir bir [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) arabirimi aracılığıyla geri çağırma. Bu olay arabirimle son değeri ile elde edilebilir [GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklayıcısı Olaylarını Çağırma](../../extensibility/debugger/calling-debugger-events.md)