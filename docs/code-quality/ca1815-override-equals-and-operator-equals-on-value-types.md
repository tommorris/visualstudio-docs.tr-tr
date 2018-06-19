---
title: 'CA1815: Değer türlerinde eşittir ve işleç eşitliklerinin üzerine yaz'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1815
- OverrideEqualsAndOperatorEqualsOnValueTypes
helpviewer_keywords:
- OverrideEqualsAndOperatorEqualsOnValueTypes
- CA1815
ms.assetid: 0a8ab3a3-ee8e-46f7-985d-dcf00c89363b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4d3fbe44347e1d0c453c2db9de1f5deac84ab771
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31914812"
---
# <a name="ca1815-override-equals-and-operator-equals-on-value-types"></a>CA1815: Değer türlerinde eşittir ve işleç eşitliklerinin üzerine yaz
|||
|-|-|
|TypeName|OverrideEqualsAndOperatorEqualsOnValueTypes|
|CheckId|CA1815|
|Kategori|Microsoft.Performance|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Bir ortak değer türü geçersiz <xref:System.Object.Equals%2A?displayProperty=fullName>, veya eşitlik işleci (==) uygulamıyor. Bu kural, numaralandırmalar denetlemez.

## <a name="rule-description"></a>Kural Tanımı
 Değer türleri, devralınan uygulanması için <xref:System.Object.Equals%2A> yansıma kitaplığı kullanır ve tüm alanları içeriğini karşılaştırır. Yansıma hesaplama açısından pahalıdır ve her alan için eşitlik karşılaştırma gereksiz olabilir. Compare veya sıralama örneği kullanıcılara beklediğiniz veya bunları karma tablosu anahtarları gibi değer türü uygulamalıdır <xref:System.Object.Equals%2A>. İşleç aşırı yüklemesi programlama diliniz destekliyorsa, eşitlik ve eşitsizlik işleçleri uygulaması sağlamanız gerekir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için uygulama sağlayın <xref:System.Object.Equals%2A>. Eşitlik işleci uygularsanız olabilir.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Değer türü örnekleri birbirlerine karşılaştırılmayacak varsa bir uyarı bu kuraldan gizlemek güvenlidir.

## <a name="example-of-a-violation"></a>Bir ihlali örneği

### <a name="description"></a>Açıklama
 Aşağıdaki örnek, bu kural ihlal eden bir yapı (değer türü) gösterir.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Performance.OverrideEqualsViolation#1](../code-quality/codesnippet/CSharp/ca1815-override-equals-and-operator-equals-on-value-types_1.cs)]

## <a name="example-of-how-to-fix"></a>Nasıl bir örneği için düzeltme

### <a name="description"></a>Açıklama
 Aşağıdaki örnek, geçersiz kılarak önceki ihlali giderir <xref:System.ValueType.Equals%2A?displayProperty=fullName> ve eşitlik işleçleri uygulama (==,! =).

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Performance.OverrideEqualsFixed#1](../code-quality/codesnippet/CSharp/ca1815-override-equals-and-operator-equals-on-value-types_2.cs)]

## <a name="related-rules"></a>İlgili kuralları
 [CA2224: Eşittir işlecini aşırı yükleyerek eşittiri geçersiz kılın](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)

 [CA2231: ValueType.Equals değerini geçersiz kılmada eşittir işlecini aşırı yükle](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)

 [CA2226: İşleçler simetrik aşırı yüklemelere sahip olmalıdır](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.Object.Equals%2A?displayProperty=fullName>