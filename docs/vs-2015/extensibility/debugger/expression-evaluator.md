---
title: İfade değerlendirici | Microsoft Docs
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
- expressions [Debugging SDK]
- debugging [Debugging SDK], expression evaluation
- expression evaluation
ms.assetid: f9381b2f-99aa-426c-aea0-d9c15f3c859b
caps.latest.revision: 20
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8856284869a256f9be08931b36db644621a3202d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686173"
---
# <a name="expression-evaluator"></a>İfade Değerlendirici
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ifade değerlendiricisi](https://docs.microsoft.com/visualstudio/extensibility/debugger/expression-evaluator).  
  
İfade değerlendiricilerini (EE), bunları IDE kesme modundayken, kullanıcı tarafından görüntülenmesine izin verme ayrıştırılamadı ve çalışma zamanında değişkenleri ve ifadeleri değerlendirin dilinin sözdizimi inceleyin.  
  
## <a name="using-expression-evaluators"></a>İfade Değerlendiricilerini kullanma  
 İfadeleri kullanarak oluşturulan [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) yöntemini aşağıdaki gibi:  
  
1.  Hata ayıklama altyapısı (DE) uygulayan [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) arabirimi.  
  
2.  Hata ayıklama paketi alır bir `IDebugExpressionContext2` nesnesinden bir [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md) arabirimi ve çağrıları `IDebugStackFrame2::ParseText` almak için yöntemi bir [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) nesne.  
  
3.  Hata ayıklama paketi çağrıları [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) yöntemi veya [EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) ifadenin değerini almak için yöntemi. `IDebugExpression2::EvaluateAsync` Komut/hemen penceresinden çağrılır. Diğer tüm kullanıcı Arabirimi bileşenleri çağırma `IDebugExpression2::EvaluateSync`.  
  
4.  İfade değerlendirmesinin sonucu olan bir [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) adı, tür ve ifade değerlendirme sonucu değerini içeren bir nesne.  
  
 İfade değerlendirme sırasında EE sembol sağlayıcısı bileşenini bilgileri gerektirir. Sembol sağlayıcısı ayrıştırılmış ifade anlama ve tanımlamak için kullanılan bir sembolik bilgi sağlar.  
  
 Zaman uyumsuz bir ifade değerlendirme işlemi tamamlandığında, zaman uyumsuz bir olay tarafından oturum hata ayıklama Yöneticisi (SDM) üzerinden DE IDE ifade değerlendirme tamamlandıktan bildirim gönderilir. Zaman uyumlu bir ifade değerlendirme işlemi tamamlandıktan sonra değerlendirme sonucu çağrısından döndürülen `IDebugExpression2::EvaluateSync` yöntemi.  
  
## <a name="implementation-notes"></a>Uygulama Notları  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Hata ayıklama motorlarını beklediğiniz ortak dil çalışma zamanı (CLR) arabirimlerini kullanarak ifade değerlendiricisi ile bahsedeceğiz. Sonuç olarak, bir ifade değerlendiricisi çalıştığını ile [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] hata ayıklama motorlarını CLR desteklemesi gerekir (tüm CLR hata ayıklama arabirimleri tam listesi parçası olan debugref.doc içinde bulunabilir, [!INCLUDE[winsdklong](../../includes/winsdklong-md.md)]).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklayıcı Bileşenleri](../../extensibility/debugger/debugger-components.md)

