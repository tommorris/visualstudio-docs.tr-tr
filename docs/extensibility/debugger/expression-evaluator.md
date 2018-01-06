---
title: "İfade değerlendirici | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- expressions [Debugging SDK]
- debugging [Debugging SDK], expression evaluation
- expression evaluation
ms.assetid: f9381b2f-99aa-426c-aea0-d9c15f3c859b
caps.latest.revision: "19"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 55aaa595c49d0c50cff5f874d1b322c3adbb9729
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="expression-evaluator"></a>İfade değerlendirici
İfade değerlendiricileri (EE) IDE kesme modunda olduğunda kullanıcı tarafından görüntülenmesine izin vermeden ayrıştırma ve çalışma zamanında değişkenleri ve ifadeler değerlendirmek için bir dil söz dizimi inceleyin.  
  
## <a name="using-expression-evaluators"></a>İfade Değerlendiricileri kullanma  
 İfadeler kullanarak oluşturulur [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) şekilde yöntemi:  
  
1.  Hata ayıklama altyapısı (DE) uygulayan [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) arabirimi.  
  
2.  Hata ayıklama paketini alır bir `IDebugExpressionContext2` nesnesinin bir [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md) arabirimi ve çağrıları `IDebugStackFrame2::ParseText` yöntemi elde etmek üzere bir [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) nesnesi.  
  
3.  Hata ayıklama paket çağrıları [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) yöntemi veya [EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) ifadesinin değerini almak için yöntemi. `IDebugExpression2::EvaluateAsync`Komut/hemen penceresinden olarak adlandırılır. Diğer tüm kullanıcı Arabirimi bileşenlerini çağrı `IDebugExpression2::EvaluateSync`.  
  
4.  İfade değerlendirme sonucu bir [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) adını, türünü ve ifade değerlendirme sonucu değerini içeren nesne.  
  
 İfade değerlendirme sırasında EE simgesi sağlayıcısı bileşeninden bilgileri gerektirir. Sembol sağlayıcı tanımlama ve ayrıştırılmış ifade anlamak için kullanılan simgesel bilgileri sağlar.  
  
 Zaman uyumsuz ifade değerlendirme tamamlandığında, zaman uyumsuz bir olay tarafından oturumu hata ayıklama Yöneticisi'ni (SDM) üzerinden DE IDE ifade değerlendirme tamamlandığını bildirmek için gönderilir. Zaman uyumlu ifade değerlendirme tamamlandığında değerlendirme sonucu için çağrısından döndürülen `IDebugExpression2::EvaluateSync` yöntemi.  
  
## <a name="implementation-notes"></a>Uygulama Notları  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Hata ayıklama motorları beklediğiniz ortak dil çalışma zamanı (CLR) arabirimleri kullanarak ifade değerlendiricisi ile iletişim kurabilecek şekilde. Sonuç olarak, bir ifade değerlendiricisi gerçekleştiğine ile [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] hata ayıklama motorları CLR desteklemesi gerekir (hata ayıklama arabirimleri tüm CLR tam bir listesi yer debugref.doc içinde bulunabilir, [!INCLUDE[winsdklong](../../deployment/includes/winsdklong_md.md)]).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklayıcı Bileşenleri](../../extensibility/debugger/debugger-components.md)