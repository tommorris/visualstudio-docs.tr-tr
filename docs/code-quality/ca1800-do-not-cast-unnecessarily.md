---
title: 'CA1800: Gereksiz atamalar yapmayın'
ms.date: 10/26/2017
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1800
- DoNotCastUnnecessarily
helpviewer_keywords:
- DoNotCastUnnecessarily
- CA1800
ms.assetid: b79a010a-6627-421e-8955-6007e32fa808
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- VB
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 78aeac772e52f27b82e41fa66224f27ebfdee342
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1800-do-not-cast-unnecessarily"></a>CA1800: Gereksiz atamalar yapmayın
|||
|-|-|
|TypeName|DoNotCastUnnecessarily|
|CheckId|CA1800|
|Kategori|Microsoft.Performance|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
Bir yöntem yinelenen atamaları biri kendi bağımsız değişkenleri veya yerel değişkenler gerçekleştirir.

Tam çözümleme için bu kural, hata ayıklama bilgileri kullanarak test edilmiş derleme oluşturulmalıdır ve ilişkili program veritabanı (.pdb) dosyası kullanılabilir olması gerekir.

## <a name="rule-description"></a>Kural Tanımı
Özellikle yayınlar sıkıştırılmış yineleme deyiminde gerçekleştirildiğinde yinelenen yayınların performansını azaltır. Açık Yinelenen atama işlemleri için bir yerel değişkende cast sonucunu depolamak ve yinelenen atama işlemleri yerine yerel değişken kullanın.

C# `is` işleci gerçek cast gerçekleştirilmeden önce dönüştürme başarılı olup olmadığını sınamak için kullanılan test göz önünde bulundurun `as` işleci yerine. Bu tarafından gerçekleştirilen örtük dönüştürme işlemi olmadan aynı işlevselliği sunar `is` işleci. Veya, C# 7.0 ve daha sonra kullanmak `is` işleciyle [desen eşleştirme](/dotnet/csharp/language-reference/keywords/is#pattern-matching-with-is) tür dönüştürme denetlemek ve bir değişkene ifadeyi bu türdeki tek bir adımda dönüştürmek için.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için cast işlemlerinin sayısını en aza indirmek için yöntem uygulaması değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Performans ilgili bir sorun değilse bir uyarı bu kuraldan gizlemek için ya da kural tamamen yoksaymak için güvenli olur.

## <a name="examples"></a>Örnekler
 Aşağıdaki örnek, C# kullanarak kuralını ihlal eden bir yöntemi gösterir `is` işleci. İkinci bir yöntem değiştirerek kural karşılayan `is` sonucu sınaması işleciyle `as` iki bir yineleme başına cast işlemlerinin sayısı azalır işleci. Ayrıca üçüncü bir yöntem kullanarak kural karşılar `is` ile [desen eşleştirme](/dotnet/csharp/language-reference/keywords/is#pattern-matching-with-is) tür dönüştürme başarılı olması istenen türde bir değişken oluşturmak için.

 [!code-csharp[FxCop.Performance.UnnecessaryCastsAsIs#1](../code-quality/codesnippet/CSharp/ca1800-do-not-cast-unnecessarily_1.cs)]

 Aşağıdaki örnek, bir yöntemi gösterir `start_Click`, kural ve bir yöntem ihlal birden çok yinelenen açık atamaları olan `reset_Click`, hangi karşılayan kural yerel bir değişkende cast depolayarak.

 [!code-vb[FxCop.Performance.UnnecessaryCasts#1](../code-quality/codesnippet/VisualBasic/ca1800-do-not-cast-unnecessarily_2.vb)]
 [!code-csharp[FxCop.Performance.UnnecessaryCasts#1](../code-quality/codesnippet/CSharp/ca1800-do-not-cast-unnecessarily_2.cs)]

## <a name="see-also"></a>Ayrıca Bkz.
[(C# Başvurusu) olarak](/dotnet/csharp/language-reference/keywords/as)
[(C# Başvurusu)](/dotnet/csharp/language-reference/keywords/is)