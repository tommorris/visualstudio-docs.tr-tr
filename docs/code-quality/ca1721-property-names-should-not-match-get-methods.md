---
title: 'CA1721: Tür adları alma metotlarıyla eşleşmemelidir'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
helpviewer_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
ms.assetid: 45a0e853-1f06-4688-af1b-cc634409e295
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 29db0561f15a16bf9b449f03f209feedf80dbd88
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1721-property-names-should-not-match-get-methods"></a>CA1721: Tür adları alma metotlarıyla eşleşmemelidir
|||
|-|-|
|TypeName|PropertyNamesShouldNotMatchGetMethods|
|CheckId|CA1721|
|Kategori|Microsoft.Naming|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Genel veya korumalı bir üyenin adını 'Get' ile başlar ve aksi halde bir genel veya korumalı özellik adıyla eşleşen. Örneğin, 'GetColor' ve 'Color' adlı bir özellik adlı bir yöntem içeren bir türü bu kural ihlal ediyor.

## <a name="rule-description"></a>Kural Tanımı
 Get yöntemleri ve özellikleri açıkça işlevlerine ayırt adlar olmalıdır.

 Adlandırma kuralları hedefleyen ortak dil çalışma zamanı kitaplıkları için genel bir bakış sağlar. Bu yeni bir yazılım kitaplığı öğrenmek için gereklidir ve kitaplık geliştirme yönetilen kodda uzmanlığa sahip olan kişi tarafından geliştirilmiştir müşteri güvenini artırır süreyi azaltır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Adı 'Get' ile önekli bir yöntemin adı eşleşmiyor şekilde değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

> [!NOTE]
>  Get yöntemini Iextenderprovider arabirimi uygulayarak neden oluyorsa bu uyarı atlanabilir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, yöntemi ve bu kural ihlal özelliği içerir.

 [!code-csharp[FxCop.Naming.GetMethod#1](../code-quality/codesnippet/CSharp/ca1721-property-names-should-not-match-get-methods_1.cs)]
 [!code-vb[FxCop.Naming.GetMethod#1](../code-quality/codesnippet/VisualBasic/ca1721-property-names-should-not-match-get-methods_1.vb)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1024: Uygun yerlerde özellikler kullanın](../code-quality/ca1024-use-properties-where-appropriate.md)