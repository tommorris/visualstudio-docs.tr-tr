---
title: 'CA2225: İşleç aşırı yüklemeleri adlandırılmış alternatiflere sahiptir'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- OperatorOverloadsHaveNamedAlternates
- CA2225
helpviewer_keywords:
- OperatorOverloadsHaveNamedAlternates
- CA2225
ms.assetid: af8f7ab1-63ad-4861-afb9-b7a7a2be15e1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1b6e95f73fbb037041aadcc95eb7336a5744ee2d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2225-operator-overloads-have-named-alternates"></a>CA2225: İşleç aşırı yüklemeleri adlandırılmış alternatiflere sahiptir
|||
|-|-|
|TypeName|OperatorOverloadsHaveNamedAlternates|
|CheckId|CA2225|
|Kategori|Microsoft.Usage|
|Yeni Değişiklik|Olmayan sonu|

## <a name="cause"></a>Sebep
 Operatör aşırı yüklemesi bulundu ve beklenen adlandırılmış alternatif yöntem bulunamadı.

## <a name="rule-description"></a>Kural Tanımı
 İşleç aşırı yüklemesi hesaplamaları için bir türü temsil etmek için simgeler kullanılmasına izin verir. Örneğin, artı (+) simgesi eklenmesi için overloads türü genellikle 'Ekle' adında bir alternatif üye gerekir. Adlandırılmış alternatif üye işleci aynı işlevselliğe erişim sağlar ve aşırı yüklenmiş işleçler desteklemeyen dillerde program geliştiriciler için sağlanır.

 Bu kural aşağıdaki tabloda listelenen işleçleri inceler.

|C#|Visual Basic|C++|Diğer adı|
|---------|------------------|-----------|--------------------|
|+ (ikili)|+|+ (ikili)|Ekle|
|+=|+=|+=|Ekle|
|&|Ve|&|BitwiseAnd|
|&=|Ve =|&=|BitwiseAnd|
|&#124;|Veya|&#124;|BitwiseOr|
|&#124;=|Veya =|&#124;=|BitwiseOr|
|--|Yok|--|Azaltma|
|/|/|/|Bölme|
|/=|/=|/=|Bölme|
|==|=|==|Eşittir|
|^|Xor|^|Xor|
|^=|Xor =|^=|Xor|
|>|>|>|{1&gt;Karşılaştır&lt;1}|
|>=|>=|>=|{1&gt;Karşılaştır&lt;1}|
|++|Yok|++|Artırma|
|<>|!=|Eşittir|
|<<|<<|<<|LeftShift|
|<<=|<<=|<<=|LeftShift|
|<|<|<|{1&gt;Karşılaştır&lt;1}|
|<=|<=|\<=|{1&gt;Karşılaştır&lt;1}|
|&&|Yok|&&|LogicalAnd|
|&#124;&#124;|Yok|&#124;&#124;|LogicalOr|
|!|Yok|!|LogicalNot|
|%|Mod|%|Mod veya kalan|
|%=|Yok|%=|Mod|
|* (ikili)|*|*|Çarp|
|*=|Yok|*=|Çarp|
|~|değil|~|OnesComplement|
|>>|>>|>>|RightShift|
=|Yok|>>=|RightShift|
|-(ikili)|-(ikili)|-(ikili)|Çıkarma|
|-=|Yok|-=|Çıkarma|
|true|IsTrue|Yok|IsTrue (özellik)|
|-(tekli)|Yok|-|Negate|
|+ (tekli)|Yok|+|artı|
|false|IsFalse|False|IsTrue (özellik)|

 Yok == seçtiğiniz dilde aşırı yüklenemez.

 Kural ayrıca bir türdeki örtük ve açık atama işleçleri denetler (`SomeType`) adlı yöntemlerini denetleyerek `ToSomeType` ve `FromSomeType`.

 İkili İşleç aşırı, C# ' ta karşılık gelen atama işleci varsa, aynı zamanda örtük olarak aşırı yüklü değildir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için işleci için alternatif yöntemini uygulayın; Önerilen diğer adı kullanarak adlandırın.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Paylaşılan bir kitaplık uyguluyorsanız, bu kural bir uyarıdan bastırmak değil. Uygulamalar bu kuraldan bir uyarıyı yok sayabilirsiniz.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bu kural ihlal eden bir yapısını tanımlar. Örnek düzeltmek için ortak bir ekleme `Add(int x, int y)` yapısına yönelik işaretçinin yöntemi.

 [!code-csharp[FxCop.Usage.OperatorOverloadsHaveNamedAlternates#1](../code-quality/codesnippet/CSharp/ca2225-operator-overloads-have-named-alternates_1.cs)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1046: Başvuru türlerinde eşittir işleçlerini aşırı yüklemeyin](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)

 [CA2226: İşleçler simetrik aşırı yüklemelere sahip olmalıdır](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

 [CA2224: Eşittir işlecini aşırı yükleyerek eşittiri geçersiz kılın](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)

 [CA2218: GetHashCode'u Eşittir'i geçersiz kılarak geçersiz kılın](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

 [CA2231: ValueType.Equals değerini geçersiz kılmada eşittir işlecini aşırı yükle](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)