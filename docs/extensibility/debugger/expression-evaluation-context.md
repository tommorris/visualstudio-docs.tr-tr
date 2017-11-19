---
title: "İfade değerlendirme bağlamının | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: expression evaluation, context
ms.assetid: a2fd3758-09bd-45ae-8ecc-2d276c0036ba
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1ac80a3fcf3a7f75be3f23dd1350da047ccbb393
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="expression-evaluation-context"></a>İfade değerlendirme bağlamı
İçinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] hata ayıklama, bir **ifade değerlendirme bağlamının**:  
  
-   İfade değerlendirme için bağlamını temsil eder. Genellikle, bir değerlendirme bağlamı değişkenleri, parametreleri, işlevleri ve yöntemleri değerlendirileceği sözcük kapsamında karşılık gelir. Örneğin, bir yığın çerçevesi ile ilişkili bir ifade değerlendirme bağlamı, yerel değişkenleri, yöntem parametreleri ve sınıf üyeleri (varsa) değerlendirmesi için bağlam sağlayacaktır.  
  
-   Bir program kesme noktasında durdurulduğunda bulunmaktadır. İfade, bağlama ve belirli bağlamda değerlendirme için hazır ayrıştırılmış bir ifadeyi temsil eden bir veri yapısıdır.  
  
     Daha ayrıntılı olarak ifadeleri kullanılarak oluşturulan [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) yöntemi. Bir ifade değerlendirildiğinde adını ve türünü değişken veya değişken ve değeri içeren yazdırılabilir bir dize oluşturur. Bu dize, Gözcü penceresi veya IDE'nin yerel öğeler penceresi görüntülenir.  
  
     Verilen bir `BSTR` ve bir [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) arabirimi, hata ayıklama altyapısı (DE) oluşturabilir bir [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) bir ifade ayrıştırma tarafından arabirimi. Verilen bir `IDebugExpression2` arabirimi DE zaman uyumlu veya zaman uyumsuz ifade değerlendirmesi ile değerli alabilirsiniz. Bu değer, değişken veya değişken, türü ve adını yanı sıra IDE görüntülenmek üzere gönderilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfade değerlendirme arabirimleri](../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [Hata ayıklayıcı bağlamları](../../extensibility/debugger/debugger-contexts.md)