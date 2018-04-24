---
title: 'CA1000: Genel türlerde statik üyeleri belirtme'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1000
- DoNotDeclareStaticMembersOnGenericTypes
helpviewer_keywords:
- DoNotDeclareStaticMembersOnGenericTypes
- CA1000
ms.assetid: 5c0da594-f8d0-4f40-953d-56bf7fbd2087
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b1e970f3b0f8cf8e774e78a5318de87d5d30d805
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1000-do-not-declare-static-members-on-generic-types"></a>CA1000: Genel türlerde statik üyeleri belirtme
|||
|-|-|
|TypeName|DoNotDeclareStaticMembersOnGenericTypes|
|CheckId|CA1000|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Dışarıdan görünür bir genel türünü içeren bir `static` (`Shared` Visual Basic'te) üyesi.

## <a name="rule-description"></a>Kural Tanımı
 Zaman bir `static` genel bir tür üyesi çağrılır, tür bağımsız değişkeni türü için belirtilmesi gerekir. Destek çıkarımı desteklenmeyen genel örnek üyesi çağrıldığında tür bağımsız değişkeni üye için belirlenmelidir. Aşağıdaki çağrıları gösterildiği gibi bu iki durumlarda tür bağımsız değişkeni belirtmek için farklı ve kolayca kafası söz dizimi:

```vb
' Shared method in a generic type.
GenericType(Of Integer).SharedMethod()

' Generic instance method that does not support inference.
someObject.GenericMethod(Of Integer)()
```

```csharp
// Static method in a generic type.
GenericType<int>.StaticMethod();

// Generic instance method that does not support inference.
someObject.GenericMethod<int>();
```

 Genellikle, tür bağımsız değişkeni, üye ne zaman çağrıldığını belirtilmesi gerekmez. böylece hem de önceki bildirimler kaçınılmalıdır. Genel türler olmayan sözdizimi Hayır farklı genel arama üyeleri için bir söz dizimi sonuçlanır. Daha fazla bilgi için bkz: [CA1004: Genel yöntemler tür parametresi sağlayacağını](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md).

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için statik üye kaldırma veya bir örnek üyesine değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın. Genel türler anlamak ve kullanmak kolay bir sözdiziminde sağlama öğrenmek için gerekli olan ve yeni kitaplıklar benimseme oranı artırır süreyi azaltır.

## <a name="related-rules"></a>İlgili kuralları
 [CA1005: Genel türlerde aşırı parametrelerden kaçının](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010: Koleksiyonlar genel arabirim uygulamalıdır](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1002: Genel listeleri gösterme](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: Üye imzalarında genel türleri iç içe kullanmayın](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004: Genel metotlar tür parametresi sağlamalıdır](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003: Genel olay işleyici örnekleri kullan](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007: Uygun yerlerde genel türler kullanın](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>Ayrıca Bkz.
 [Genel Türler](/dotnet/csharp/programming-guide/generics/index)