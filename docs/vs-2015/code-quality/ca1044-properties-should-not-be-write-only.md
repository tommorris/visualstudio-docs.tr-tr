---
title: 'CA1044: Özellikler salt olmamalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- PropertiesShouldNotBeWriteOnly
- CA1044
helpviewer_keywords:
- CA1044
- PropertiesShouldNotBeWriteOnly
ms.assetid: 8386bf3a-b161-4841-bf8b-92591595aea9
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 732af1dcdeff669723f717dabe035a38640a8bf3
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902996"
---
# <a name="ca1044-properties-should-not-be-write-only"></a>CA1044: Özellikler salt yazılır olmamalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1044: özellikler salt olmamalıdır](https://docs.microsoft.com/visualstudio/code-quality/ca1044-properties-should-not-be-write-only).

|||
|-|-|
|TypeName|PropertiesShouldNotBeWriteOnly|
|CheckId|CA1044|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Ortak veya korumalı özellik ayarlama erişimcisine sahip ancak get erişimcisine sahip değildir.

## <a name="rule-description"></a>Kural Tanımı
 Alma erişimcisi bir özelliği okuma erişimi ve set erişimcileri yazma erişimi sağlar. Salt okunur özelliğe sahip olmasına karşın kabul edilebilir ve genellikle gereklidir, tasarıma ilişkin yönergeler salt yazılır özellik kullanılmasını engeller. Bunun nedeni, bir kullanıcı bir değere ayarlayın, ve ardından kullanıcı değeri görüntülemeyi engellerse herhangi bir güvenlik sağlamaz. Ayrıca, okuma erişimi olmadan, yararsız olduklarını sınırlayan paylaşılan nesnelerin durumu görüntülenemez.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlalini düzeltmek için özelliği bir alma erişimcisi ekleyin. Salt yazılır özelliği davranışını gerekliyse, alternatif olarak, bu özelliği yönteme dönüştürmek göz önünde bulundurun.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan bir uyarıyı bastırmayın önemle tavsiye edilir.

## <a name="example"></a>Örnek
 Aşağıdaki örnekte, `BadClassWithWriteOnlyProperty` salt yazma özelliğine sahip bir tür. `GoodClassWithReadWriteProperty` Düzeltilen kod içerir.

 [!code-csharp[FxCop.Design.PropertiesNotWriteOnly#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.PropertiesNotWriteOnly/cs/FxCop.Design.PropertiesNotWriteOnly.cs#1)]
 [!code-vb[FxCop.Design.PropertiesNotWriteOnly#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.PropertiesNotWriteOnly/vb/PropertiesNotWriteOnly.vb#1)]



