---
title: 'CA1501: Aşırı devralmadan kaçın'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1501
- AvoidExcessiveInheritance
helpviewer_keywords:
- AvoidExcessiveInheritance
- CA1501
ms.assetid: 9e934746-1a4d-492a-91e4-085201abafa4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 488ab877764b0b7dcd3c14885387c4a58115d5df
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1501-avoid-excessive-inheritance"></a>CA1501: Aşırı devralmadan kaçın
|||
|-|-|
|TypeName|AvoidExcessiveInheritance|
|CheckId|CA1501|
|Kategori|Microsoft.Maintainability|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Devralma hiyerarşisinde düzeyleri dörtten fazla olan türdür.

## <a name="rule-description"></a>Kural Tanımı
 İç içe yuvalanmış hiyerarşileri izlemek, anlamak ve muhafaza etmek zor olabilir. Bu kural analiz aynı modülde hiyerarşileri için sınırlar.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için türü devralma hiyerarşisinde daha az ayrıntılı bir taban türü öğesinden türetilmeli veya Ara temel türlerinden bazıları ortadan kaldırmak.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural bir uyarıdan gizlemek güvenlidir. Bununla birlikte, kod korumak daha zor olabilir. Taban türleri görünürlüğünü bağlı olarak, bu kuralı ihlallerini çözümleme önemli değişiklikler oluşturabilir, unutmayın. Örneğin, ortak bir taban türleri kaldırma önemli bir değişiklik olur.

## <a name="example"></a>Örnek
 Aşağıdaki örnek kuralını ihlal eden bir tür gösterir.

 [!code-csharp[FxCop.Maintainability.ExcessiveInheritance#1](../code-quality/codesnippet/CSharp/ca1501-avoid-excessive-inheritance_1.cs)]
 [!code-vb[FxCop.Maintainability.ExcessiveInheritance#1](../code-quality/codesnippet/VisualBasic/ca1501-avoid-excessive-inheritance_1.vb)]