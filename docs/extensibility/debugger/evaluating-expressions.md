---
title: İfadeleri değerlendirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- expressions [Debugging SDK], evaluating
- debugging [Debugging SDK], expression evaluation
- expression evaluation
ms.assetid: 5ccfcc80-dea5-48a1-8bae-6a26f8d3bc56
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 47de275d63f5be1743408aa93c971dcff2959c25
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31102798"
---
# <a name="evaluating-expressions"></a>İfadeleri değerlendirme
İfadeleri otomatik değişkenler, izleme, QuickWatch veya hemen windows geçirilen dizelerden oluşturulur. Bir ifade değerlendirildiğinde adını ve türünü değişken veya değişken ve değeri içeren yazdırılabilir bir dize oluşturur. Bu dize karşılık gelen IDE penceresinde görüntülenir.  
  
## <a name="implementation"></a>Uygulama  
 Bir program kesme noktasında durdurulduğunda ifadeler değerlendirilir. İfade tarafından temsil edilen bir [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) bağlama ve verilen ifade değerlendirme bağlamı içinde değerlendirme için hazır ayrıştırılmış bir ifadeyi temsil eden arabirim. Yığın çerçevesi uygulayarak hata ayıklama altyapısı (DE) sağlayan ifade değerlendirme bağlamı belirler [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) arabirimi.  
  
 Kullanıcı dizesini verilen bir [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) arabirimi, hata ayıklama altyapısı (DE) elde edebilirsiniz bir [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) kullanıcı dizeye geçirerek arabirimi [ IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) yöntemi. Döndürülen IDebugExpression2 arabirimi değerlendirme için hazır ayrıştırılmış ifade içeriyor.  
  
 İle `IDebugExpression2` arabirimi DE zaman uyumlu veya zaman uyumsuz ifade değerlendirmesi aracılığıyla ifadesinin değerini alabilirsiniz kullanarak [IDebugExpression2::EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) veya [IDebugExpression2:: EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md). Bu değer, değişken veya değişken, türü ve adını yanı sıra IDE görüntülenmek üzere gönderilir. Değer, adı ve türü tarafından gösterilen bir [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) arabirimi.  
  
 İfade değerlendirme etkinleştirmek için bir DE uygulamalıdır [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) ve [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) arabirimleri. Zaman uyumlu ve zaman uyumsuz değerlendirme uygulanması gerekir [IDebugProperty2::GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yığın çerçeveleri](../../extensibility/debugger/stack-frames.md)   
 [İfade değerlendirme bağlamı](../../extensibility/debugger/expression-evaluation-context.md)   
 [Hata Ayıklama Görevleri](../../extensibility/debugger/debugging-tasks.md)