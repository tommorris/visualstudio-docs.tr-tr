---
title: 'CA1007: Uygun yerlerde genel türler kullanın'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1007
- UseGenericsWhereAppropriate
helpviewer_keywords:
- CA1007
- UseGenericsWhereAppropriate
ms.assetid: eab780ea-3b1f-4d32-b15a-5d48da2df46b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6379a811da7c62be59a322ee68ad9f030d9693d9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31899723"
---
# <a name="ca1007-use-generics-where-appropriate"></a>CA1007: Uygun yerlerde genel türler kullanın
|||
|-|-|
|TypeName|UseGenericsWhereAppropriate|
|CheckId|CA1007|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Türünde bir başvuru parametresi dışarıdan görünür bir yöntem içerir <xref:System.Object?displayProperty=fullName>ve içeren derleme hedefleri [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)].

## <a name="rule-description"></a>Kural Tanımı
 Bir başvuru parametresi kullanılarak değiştirilebilir bir parametre olan `ref` (`ByRef` içinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) anahtar sözcüğü. Bir başvuru parametresi için sağlanan bağımsız değişken türü başvurusu parametre türüyle tam olarak eşleşmelidir. Başvuru parametre türünden türetilmiş bir tür kullanmak için türü öncelikle cast ve başvuru parametre türü bir değişkene atanır. Genel yöntem başvuru parametre türü türe ilk atama olmadan yönteme iletilecek kısıtlamaları tabi tüm türleri izin verir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için yöntem genel yapmak ve Değiştir <xref:System.Object> bir tür parametresi kullanılarak parametre.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Aşağıdaki örnek nongeneric ve genel yöntemleri olarak uygulanan bir genel amaçlı değiştirme yordamı gösterir. Nongeneric yöntemi kıyasla genel yöntemini kullanarak dizeleri nasıl verimli bir şekilde değiştirilen unutmayın.

 [!code-vb[FxCop.Design.UseGenerics#1](../code-quality/codesnippet/VisualBasic/ca1007-use-generics-where-appropriate_1.vb)]
 [!code-csharp[FxCop.Design.UseGenerics#1](../code-quality/codesnippet/CSharp/ca1007-use-generics-where-appropriate_1.cs)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1005: Genel türlerde aşırı parametrelerden kaçının](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010: Koleksiyonlar genel arabirim uygulamalıdır](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000: Genel türlerde statik üyeleri belirtme](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: Genel listeleri gösterme](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: Üye imzalarında genel türleri iç içe kullanmayın](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004: Genel metotlar tür parametresi sağlamalıdır](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003: Genel olay işleyici örnekleri kullan](../code-quality/ca1003-use-generic-event-handler-instances.md)

## <a name="see-also"></a>Ayrıca Bkz.
 [Genel Türler](/dotnet/csharp/programming-guide/generics/index)