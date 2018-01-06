---
title: "Bakım uyarıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.maintainabilityrules
helpviewer_keywords:
- warnings, maintainability
- managed code analysis warnings, maintainability warnings
- maintainability warnings
ms.assetid: 537e70ca-a88c-49df-bfc7-0ee63bbe4f16
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8d432dab79d5cd88d398a74c352cc9d34c8b4f2e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="maintainability-warnings"></a>Bakım Uyarıları
Bakım uyarıları kitaplığı ve uygulama bakım destekler.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA1500: Değişken adları alan adlarıyla eşleşmemelidir](../code-quality/ca1500-variable-names-should-not-match-field-names.md)|Örnek yöntemi, bir parametre veya hatalar için müşteri adayları bildiri türü ait bir örnek alanı adıyla eşleşen bir yerel değişken bildirir.|  
|[CA1501: Aşırı devralmadan kaçının](../code-quality/ca1501-avoid-excessive-inheritance.md)|Devralma hiyerarşisinde düzeyleri dörtten fazla olan türdür. İç içe yuvalanmış hiyerarşileri izlemek, anlamak ve muhafaza etmek zor olabilir.|  
|[CA1502: Aşırı karmaşıklıktan kaçının](../code-quality/ca1502-avoid-excessive-complexity.md)|Bu kural, sayılarla ve şartlı şubelerle tanımlanan, yönteme giden doğrusal bağımsız yolların sayısını ölçer.|  
|[CA1504: Yanlış alan adlarını gözden geçirin](../code-quality/ca1504-review-misleading-field-names.md)|Örnek alanı adını, "s_" ya da statik adını başlatılır (paylaşılan [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) alanı "m_" ile başlar.|  
|[CA1505: Bakımı yapılamayan kodlardan kaçının](../code-quality/ca1505-avoid-unmaintainable-code.md)|Bir tür veya yöntemin düşük bakım dizin değeri vardır. Düşük bakım dizini muhtemelen koruması zor olan ve yeniden tasarım için iyi bir aday olan tür veya yöntemi içerir.|  
|[CA1506: Aşırı sınıf bağlantısından kaçının](../code-quality/ca1506-avoid-excessive-class-coupling.md)|Bu kural türü veya yöntemini içeren benzersiz türde başvuru sayısı belirlenerek eşlenmesiyle sınıfı ölçer.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen Kodun Ölçüm Karmaşıklığı ve Bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)