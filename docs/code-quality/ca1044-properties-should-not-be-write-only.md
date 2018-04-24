---
title: 'CA1044: Özellikler salt yazılır olmamalıdır'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- PropertiesShouldNotBeWriteOnly
- CA1044
helpviewer_keywords:
- CA1044
- PropertiesShouldNotBeWriteOnly
ms.assetid: 8386bf3a-b161-4841-bf8b-92591595aea9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 204108ed86d37594d7debc0a69139a7f2a28a44a
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1044-properties-should-not-be-write-only"></a>CA1044: Özellikler salt yazılır olmamalıdır
|||
|-|-|
|TypeName|PropertiesShouldNotBeWriteOnly|
|CheckId|CA1044|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Genel veya korumalı özellik bir set erişimcisine sahip, ancak bir get erişimcisine sahip değil.

## <a name="rule-description"></a>Kural Tanımı
 Alma erişimciler bir özelliği okuma erişimi sağlamak ve set erişimcileri yazma erişimi sağlar. Salt okunur özelliğe sahip olmasına karşın kabul edilebilir ve genellikle gereklidir, tasarıma ilişkin yönergeler salt yazılır özellik kullanılmasını engeller. Bir kullanıcı bir değer Ayarla izin vererek çünkü ve ardından kullanıcı değeri görüntülemenizi engelliyor tüm güvenlik sağlamaz. Ayrıca, okuma erişimi olmadan, yararsız olduklarını sınırlayan paylaşılan nesnelerin durumu görüntülenemez.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için bir get erişimcisine özelliğine ekleyin. Salt yazılır özellik davranışını gerekliyse, alternatif olarak, bu özelliği yönteme dönüştürmek için göz önünde bulundurun.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural bir uyarıdan engelleme önerilir.

## <a name="example"></a>Örnek
 Aşağıdaki örnekte, `BadClassWithWriteOnlyProperty` salt yazılır özelliği ile bir tür. `GoodClassWithReadWriteProperty` Düzeltilmiş kodunu içerir.

 [!code-vb[FxCop.Design.PropertiesNotWriteOnly#1](../code-quality/codesnippet/VisualBasic/ca1044-properties-should-not-be-write-only_1.vb)]
 [!code-csharp[FxCop.Design.PropertiesNotWriteOnly#1](../code-quality/codesnippet/CSharp/ca1044-properties-should-not-be-write-only_1.cs)]