---
title: 'CA1005: Genel türlerde aşırı parametrelerden kaçının'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
helpviewer_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
ms.assetid: 372b2f28-5c59-4815-9753-6c65b2bb3589
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 05dd6e6c27ed440cf17862ea635210682bcd9cf5
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1005-avoid-excessive-parameters-on-generic-types"></a>CA1005: Genel türlerde aşırı parametrelerden kaçının
|||
|-|-|
|TypeName|AvoidExcessiveParametersOnGenericTypes|
|CheckId|CA1005|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Dışarıdan görünür bir genel tür ikiden fazla tür parametresi var.

## <a name="rule-description"></a>Kural Tanımı
 Daha çok tip parametresi, genel tip içerir, bilmek daha zordur ve hangi tip parametrelerinin temsil ettiğini anımsamak zordur. Giriş olarak bir tür parametresi ile genellikle belirgin `List<T>`ve bazı durumlarda da olarak iki tür parametreleri ile `Dictionary<TKey, TValue>`. İkiden fazla tür parametreleri varsa zorluk çoğu kullanıcı için çok büyük olur (örneğin, `TooManyTypeParameters<T, K, V>` C# veya `TooManyTypeParameters(Of T, K, V)` içinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için ikiden fazla tür parametreleri kullanmak için tasarımı değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Tasarım kesinlikle ikiden fazla tür parametreleri gerektirmedikçe bu kuraldan bir uyarı bastırma değil. Genel türler anlamak ve kullanmak kolay bir sözdiziminde sağlama öğrenmek için gerekli olan ve yeni kitaplıklar benimseme oranı artırır süreyi azaltır.

## <a name="related-rules"></a>İlgili kuralları
 [CA1010: Koleksiyonlar genel arabirim uygulamalıdır](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000: Genel türlerde statik üyeleri belirtme](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: Genel listeleri gösterme](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: Üye imzalarında genel türleri iç içe kullanmayın](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004: Genel metotlar tür parametresi sağlamalıdır](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003: Genel olay işleyici örnekleri kullan](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007: Uygun yerlerde genel türler kullanın](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>Ayrıca Bkz.
 [Genel Türler](/dotnet/csharp/programming-guide/generics/index)