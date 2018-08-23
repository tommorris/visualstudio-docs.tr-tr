---
title: Kesme modunda ifade değerlendirme | Microsoft Docs
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
- break mode, expression evaluation
- debugging [Debugging SDK], expression evaluation
- expression evaluation, break mode
ms.assetid: 34fe5b58-15d5-4387-a266-72120f90a4b6
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a74119edfb390dab0a8ce0fddd96046ca80ad92d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688177"
---
# <a name="expression-evaluation-in-break-mode"></a>Kesme Modunda İfade Değerlendirme
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [kesme modunda ifade değerlendirme](https://docs.microsoft.com/visualstudio/extensibility/debugger/expression-evaluation-in-break-mode).  
  
Hata ayıklayıcı kesme modundayken ve ifade değerlendirmesi gerçekleştirin gerekir oluşan süreci açıklanmaktadır.  
  
## <a name="expression-evaluation-process"></a>İfade değerlendirme işlemi  
 Bir ifadenin değerlendirilmesi ilgili temel adımlar şunlardır:  
  
1.  Oturum hata ayıklama Yöneticisi (SDM) çağıran [IDebugStackFrame2::GetExpressionContext](../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) bir ifade bağlam arabirimi almak için [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md).  
  
2.  SDM sonra çağıran [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) ayrıştırılacak dize ile.  
  
3.  Hatanın nedenini ParseText S_OK döndürmezse döndürülür.  
  
     -Aksi takdirde-  
  
     ParseText S_OK döndürürse SDM sonra ya da çağırabilir [IDebugExpression2::EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) veya [IDebugExpression2::EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) ayrıştırılmış ifadedeki son değer elde edilir.  
  
    -   Kullanarak söz konusu olduğunda `IDebugExpression2::EvaluateSync`, belirtilen geri arama arabirimi değerlendirmeye devam eden işlemi iletişim kurmak için kullanılır. Son değeri döndürülür bir [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) arabirimi.  
  
    -   Kullanarak söz konusu olduğunda `IDebugExpression2::EvaluateAsync`, belirtilen geri arama arabirimi değerlendirmeye devam eden işlemi iletişim kurmak için kullanılır. Değerlendirme tamamlandıktan sonra EvaluateAsync gönderen bir [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) arabirimi aracılığıyla geri çağırma. Bu olay arabirimi ile son değeri ile alınabilir [GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklayıcısı Olaylarını Çağırma](../../extensibility/debugger/calling-debugger-events.md)

