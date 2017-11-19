---
title: "CA2225: İşleç aşırı yüklemeleri adlandırılmış Alternatiflere sahiptir | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OperatorOverloadsHaveNamedAlternates
- CA2225
helpviewer_keywords:
- OperatorOverloadsHaveNamedAlternates
- CA2225
ms.assetid: af8f7ab1-63ad-4861-afb9-b7a7a2be15e1
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 07d15e5ec123e645a7607f16b6020487d4c0fc2a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
|>|>|>|Karşılaştırma|  
|>=|>=|>=|Karşılaştırma|  
|++|Yok|++|Artırma|  
|<>|!=|Eşittir|  
|<<|<<|<<|LeftShift|  
|<<=|<<=|<<=|LeftShift|  
|<|<|<|Karşılaştırma|  
|<=|<=|\<=|Karşılaştırma|  
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
 [CA1046: başvuru türlerinde eşittir işlecini aşırı yüklemeyin](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)  
  
 [CA2226: İşleçler simetrik aşırı olması gerekir](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)  
  
 [CA2224: eşittir işlecini aşırı yüklemesi üzerinde geçersiz kılma eşittir](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)  
  
 [CA2218: gethashcode'u eşittir'i geçersiz kılarak geçersiz kılın](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)  
  
 [CA2231: ValueType.Equals geçersiz kılma üzerinde aşırı işleci eşittir.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)