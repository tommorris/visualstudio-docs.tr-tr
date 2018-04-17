---
title: İfade değerlendirme (Visual Studio SDK hata ayıklama) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation
ms.assetid: 5044ced5-c18c-4534-b0bf-cc3e50cd57ac
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 022a0ee21b7a58fdd69249b240490fc3c1df8361
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="expression-evaluation-visual-studio-debugging-sdk"></a>İfade değerlendirme (Visual Studio SDK hata ayıklama)
Kesme modunda IDE programınızın çeşitli değişkenler içeren basit ifadeler değerlendirebilir olması gerekir. Hata ayıklama altyapısı (DE), bunu başarmak için ayrıştırma ve IDE windows birine girilen bir ifade değerlendirme kurabilmesi gerekir.  
  
 İfadeler kullanarak oluşturulur [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) yöntemi ve bu temsil elde edilen tarafından [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) arabirimi.  
  
 **IDebugExpression2** arabirimi DE ve çağrıları tarafından uygulanan kendi **EvalAsync** döndürülecek yöntemi bir [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) görüntülemek için IDE arabirimi IDE içinde ifade değerlendirme sonuçları. [IDebugProperty2::GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) bir ifadenin değerini Gözcü penceresi veya yerel öğeler penceresi yerleştirme için kullanılabilir bir yapı döndürür.  
  
 Hata ayıklama paket veya oturum hata ayıklama Yöneticisi (SDM) çağırır [IDebugExpression2::EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) veya [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) almak için bir [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) temsil eden arabirim Değerlendirme sonucu. `IDebugProperty2` adını, türünü ve değerini döndüren yöntemler vardır. Bu bilgiler çeşitli hata ayıklayıcı pencerelerde görüntülenir.  
  
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