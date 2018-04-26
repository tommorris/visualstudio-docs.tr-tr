---
title: Bakım Uyarıları
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- vs.codeanalysis.maintainabilityrules
helpviewer_keywords:
- warnings, maintainability
- managed code analysis warnings, maintainability warnings
- maintainability warnings
ms.assetid: 537e70ca-a88c-49df-bfc7-0ee63bbe4f16
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 058dca04aba85a8c00e5f587deccf0940f71d4c5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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