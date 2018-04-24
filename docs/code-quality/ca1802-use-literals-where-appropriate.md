---
title: 'CA1802: Uygun Yerlerde Sabitleri Kullan'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UseLiteralsWhereAppropriate
- CA1802
helpviewer_keywords:
- UseLiteralsWhereAppropriate
- CA1802
ms.assetid: 2515e4cd-9e61-486d-b067-58ba1a743ce4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 861e03251a8d3f8ee461b82afdbc6ff55b254684
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1802-use-literals-where-appropriate"></a>CA1802: Uygun Yerlerde Sabitleri Kullan
|||
|-|-|
|TypeName|UseLiteralsWhereAppropriate|
|CheckId|CA1802|
|Kategori|Microsoft.Performance|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Bir alan bildirilmiş `static` ve `readonly` (`Shared` ve `ReadOnly` içinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) ve derleme zamanında computable olan bir değer ile başlatıldı.

## <a name="rule-description"></a>Kural Tanımı
 Değeri bir `static``readonly` alan bildiri türü statik Oluşturucusu çağrıldığında çalışma zamanında hesaplanır. Varsa `static``readonly` alan onu bildirilmiş ve bir statik Oluşturucu açıkça derleyicisi yayar alan başlatmak için statik bir oluşturucu bildirilmedi başlatılır.

 Değeri bir `const` alan derleme zamanında hesaplanır ve için karşılaştırıldığında, çalışma zamanı performansı artırır meta verileri, depolanan bir `static``readonly` alan.

 Hedeflenen alanına atanan değer derleme zamanında computable olduğundan, bildirimine değiştirme bir `const` derleme zamanında yerine çalışma zamanında hesaplanan değer böylece alan.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için yerini `static` ve `readonly` ile değiştiricileri `const` değiştiricisi.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Performans sorunu değilse bir uyarı bu kuraldan bastırmak veya kuralı devre dışı bırakmak daha güvenlidir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bir tür gösterir `UseReadOnly`, kural ve bir tür ihlal `UseConstant`, kural karşılar.

 [!code-vb[FxCop.Performance.UseLiterals#1](../code-quality/codesnippet/VisualBasic/ca1802-use-literals-where-appropriate_1.vb)]
 [!code-csharp[FxCop.Performance.UseLiterals#1](../code-quality/codesnippet/CSharp/ca1802-use-literals-where-appropriate_1.cs)]