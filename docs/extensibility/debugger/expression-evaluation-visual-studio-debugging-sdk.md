---
title: "İfade değerlendirme (Visual Studio SDK hata ayıklama) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation
ms.assetid: 5044ced5-c18c-4534-b0bf-cc3e50cd57ac
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ed0e494cc0efd48ea3c22d9fd881aafec42a984b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="expression-evaluation-visual-studio-debugging-sdk"></a>İfade değerlendirme (Visual Studio SDK hata ayıklama)
Kesme modunda IDE programınızın çeşitli değişkenler içeren basit ifadeler değerlendirebilir olması gerekir. Hata ayıklama altyapısı (DE), bunu başarmak için ayrıştırma ve IDE windows birine girilen bir ifade değerlendirme kurabilmesi gerekir.  
  
 İfadeler kullanarak oluşturulur [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) yöntemi ve bu temsil elde edilen tarafından [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) arabirimi.  
  
 **IDebugExpression2** arabirimi DE ve çağrıları tarafından uygulanan kendi **EvalAsync** döndürülecek yöntemi bir [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) görüntülemek için IDE arabirimi IDE içinde ifade değerlendirme sonuçları. [IDebugProperty2::GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) bir ifadenin değerini Gözcü penceresi veya yerel öğeler penceresi yerleştirme için kullanılabilir bir yapı döndürür.  
  
 Hata ayıklama paket veya oturum hata ayıklama Yöneticisi (SDM) çağırır [IDebugExpression2::EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) veya [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) almak için bir [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) temsil eden arabirim Değerlendirme sonucu. `IDebugProperty2`adını, türünü ve değerini döndüren yöntemler vardır. Bu bilgiler çeşitli hata ayıklayıcı pencerelerde görüntülenir.  
  
## <a name="using-expression-evaluation"></a>İfade değerlendirme kullanma  
 İfade değerlendirme kullanmak için uygulamanız gereken [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) yöntemi ve tüm yöntemlerinden birini [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) aşağıdaki tabloda gösterildiği gibi arabirim.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)|Zaman uyumsuz olarak bir ifadeyi değerlendirir.|  
|[Durdurma](../../extensibility/debugger/reference/idebugexpression2-abort.md)|Zaman uyumsuz ifade değerlendirme sona erer.|  
|[EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)|Bir ifadeyi zaman uyumlu olarak değerlendirir.|  
  
 Zaman uyumlu ve zaman uyumsuz değerlendirme uygulanması gerekir [IDebugProperty2::GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) yöntemi. Zaman uyumsuz ifade değerlendirme gerektirir uygulanması [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yürütme Denetimi ve Durum Değerlendirmesi](../../extensibility/debugger/execution-control-and-state-evaluation.md)