---
title: 'CA2224: Eşittir işlecini aşırı yükleyerek eşittiri geçersiz kılın'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2224
- OverrideEqualsOnOverloadingOperatorEquals
- OverrideEqualsOnOverridingOperatorEquals
helpviewer_keywords:
- OverrideEqualsOnOverloadingOperatorEquals
- CA2224
ms.assetid: 7312afd9-84ba-417f-923e-7a159b53bf70
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f8836644e109e37855aa79dc67b461591b273786
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2224-override-equals-on-overloading-operator-equals"></a>CA2224: Eşittir işlecini aşırı yükleyerek eşittiri geçersiz kılın
|||
|-|-|
|TypeName|OverrideEqualsOnOverloadingOperatorEquals|
|CheckId|CA2224|
|Kategori|Microsoft.Usage|
|Yeni Değişiklik|Olmayan sonu|

## <a name="cause"></a>Sebep
 Bir ortak türü eşitlik işleci uygular, ancak geçersiz <xref:System.Object.Equals%2A?displayProperty=fullName>.

## <a name="rule-description"></a>Kural Tanımı
 Eşitlik işleci işlevselliğini erişmek üzere sözdizimsel olarak kolay bir yol olması amaçlanmıştır <xref:System.Object.Equals%2A> yöntemi. Eşitlik işleci uygularsanız, mantığını olarak aynı olmalıdır <xref:System.Object.Equals%2A>.

 Bu kural, kodunuzu ihlal ediyor, C# Derleyici bir uyarı verir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için eşitlik işleci uyarlamasını kaldırmak, ya da geçersiz kılma <xref:System.Object.Equals%2A> ve sahip iki yöntemden dönüş değerleri aynı. Eşitlik işleci tutarsız davranışa sunmaz, uygulaması sağlayarak ihlali düzeltebilirsiniz <xref:System.Object.Equals%2A> çağırır <xref:System.Object.Equals%2A> yöntemi temel sınıf.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Eşitlik işleci devralınan uygulaması ile aynı değere döndürürse bu kuraldan bir uyarı bastırma güvenlidir <xref:System.Object.Equals%2A>. Örnek bölüm bu kural bir uyarıdan güvenle bastırmak bir tür içerir.

## <a name="examples-of-inconsistent-equality-definitions"></a>Tutarsız eşitlik tanımları örnekleri

### <a name="description"></a>Açıklama
 Aşağıdaki örnek eşitlik tutarsız tanımlarını türüyle gösterir. `BadPoint` özel bir eşitlik işleci uygulamasını sağlayarak eşitlik anlamını değiştirir, ancak geçersiz <xref:System.Object.Equals%2A> böylece aynı şekilde davranır.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Usage.OperatorEqualsRequiresEquals#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_1.cs)]

## <a name="example"></a>Örnek
 Aşağıdaki kod davranışını testleri `BadPoint`.

 [!code-csharp[FxCop.Usage.TestOperatorEqualsRequiresEquals#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_2.cs)]

 Bu örnek şu çıkışı üretir.

 **= ([0] 1,1) ve b = ([1] 2,2) eşit? Hayır**
**bir b ==? Hayır**
**a1 ve bir eşit? Evet**
**a1 == bir? Evet**
**b ve bcopy eşit? Hayır**
**b bcopy ==? Evet**
## <a name="example"></a>Örnek
 Aşağıdaki örnek, teknik olarak bu kural ihlal ediyor, ancak tutarsız bir şekilde davranır olmayan bir tür gösterir.

 [!code-csharp[FxCop.Usage.ValueTypeEquals#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_3.cs)]

## <a name="example"></a>Örnek
 Aşağıdaki kod davranışını testleri `GoodPoint`.

 [!code-csharp[FxCop.Usage.TestValueTypeEquals#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_4.cs)]

 Bu örnek şu çıkışı üretir.

 **= (1,1) ve b = (2,2) eşit? Hayır**
**bir b ==? Hayır**
**a1 ve bir eşit? Evet**
**a1 == bir? Evet**
**b ve bcopy eşit? Evet**
**b bcopy ==? Evet**
## <a name="class-example"></a>Sınıf örneği

### <a name="description"></a>Açıklama
 Aşağıdaki örnek, bu kural ihlal eden bir sınıfı (başvuru türü) gösterir.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Usage.OverrideEqualsClassViolation#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_5.cs)]

## <a name="example"></a>Örnek
 Aşağıdaki örnek, geçersiz kılarak ihlali giderir <xref:System.Object.Equals%2A?displayProperty=fullName>.

 [!code-csharp[FxCop.Usage.OverrideEqualsClassFixed#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_6.cs)]

## <a name="structure-example"></a>Yapısı örneği

### <a name="description"></a>Açıklama
 Aşağıdaki örnek, bu kural ihlal eden bir yapı (değer türü) gösterir.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Usage.OverrideEqualsStructViolation#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_7.cs)]

## <a name="example"></a>Örnek
 Aşağıdaki örnek, geçersiz kılarak ihlali giderir <xref:System.ValueType.Equals%2A?displayProperty=fullName>.

 [!code-csharp[FxCop.Usage.OverrideEqualsStructFixed#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_8.cs)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1046: Başvuru türlerinde eşittir işleçlerini aşırı yüklemeyin](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)

 [CA2225: İşleç aşırı yüklemeleri adlandırılmış alternatiflere sahiptir](../code-quality/ca2225-operator-overloads-have-named-alternates.md)

 [CA2226: İşleçler simetrik aşırı yüklemelere sahip olmalıdır](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

 [CA2218: GetHashCode'u Eşittir'i geçersiz kılarak geçersiz kılın](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

 [CA2231: ValueType.Equals değerini geçersiz kılmada eşittir işlecini aşırı yükle](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)