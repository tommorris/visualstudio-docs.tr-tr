---
title: 'CA1715: Tanımlayıcıların önekleri doğru olmalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1715
- IdentifiersShouldHaveCorrectPrefix
helpviewer_keywords:
- IdentifiersShouldHaveCorrectPrefix
- CA1715
ms.assetid: cf45f8df-6855-4cb6-a4e2-7cfed714cf2f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 883b5a5a00f5be3203b8113103193dd3e597ddfd
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31916031"
---
# <a name="ca1715-identifiers-should-have-correct-prefix"></a>CA1715: Tanımlayıcıların önekleri doğru olmalıdır
|||
|-|-|
|TypeName|IdentifiersShouldHaveCorrectPrefix|
|CheckId|CA1715|
|Kategori|Microsoft.Naming|
|Yeni Değişiklik|-Arabirimlerde harekete zaman kesiliyor.<br /><br /> Genel tür parametreleri oluştuğunda bölünemez -.|

## <a name="cause"></a>Sebep
 Dışarıdan görünür arabirim adı bir büyük harf 'ı ile' başlatılmaz.

 -veya-

 Harici olarak görünen türü veya yöntemi genel tür parametresinin adı ile bir büyük harf 'T başlamıyor '.

## <a name="rule-description"></a>Kural Tanımı
 Kurala göre bazı programlama öğeleri adlarını belirli bir önek ile başlatın.

 Arabirim adları 'I' başka bir büyük harf tarafından izlenen büyük harf ile başlamalıdır. Bu kural ihlalleri 'MyInterface' ve 'IsolatedInterface' gibi arabirimi adları için raporlar.

 Genel tür parametresi adları başlamalıdır bir büyük harf ile 'T' ve isteğe bağlı olarak başka bir büyük harf tarafından takip edilebilir. Bu kural ihlalleri 'V' ve 'Type' gibi genel tür parametresi adları için raporlar.

 Adlandırma kuralları hedefleyen ortak dil çalışma zamanı kitaplıkları için genel bir bakış sağlar. Bu, yeni yazılım kitaplıkları için gereklidir ve kitaplık geliştirme yönetilen kodda uzmanlığa sahip olan kişi tarafından geliştirilmiştir müşteri güvenini artırır öğrenme eğrisini azaltır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Böylece doğru önek tanımlayıcı yeniden adlandırın.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 **Aşağıdaki örnek yanlış adlandırılmış bir arabirimi gösterir.**

 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_1.cpp)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_1.vb)]
 [!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_1.cs)]

## <a name="example"></a>Örnek
 **Aşağıdaki örnek, önceki ihlali 'I' arabirimi ekleyerek giderir.**

 [!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_2.cs)]
 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_2.cpp)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_2.vb)]

## <a name="example"></a>Örnek
 **Aşağıdaki örnekte bir hatalı adlandırılmış genel tür parametresi gösterir.**

 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_3.cpp)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_3.vb)]
 [!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_3.cs)]

## <a name="example"></a>Örnek
 **Aşağıdaki örnek genel tür parametresi 'T ekleyerek önceki ihlali giderir '.**

 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_4.cpp)]
 [!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_4.cs)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_4.vb)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1722: Tanımlayıcıların önekleri yanlış olmamalıdır](../code-quality/ca1722-identifiers-should-not-have-incorrect-prefix.md)