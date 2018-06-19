---
title: 'CA1014: Derlemeleri CLSCompliantAttribute ile işaretleme'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
helpviewer_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
ms.assetid: 4fe57449-cf45-4745-bcd2-6345f1ed266d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 51e5a43a402bb215a939b37354dd30f24e4d5d14
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31898186"
---
# <a name="ca1014-mark-assemblies-with-clscompliantattribute"></a>CA1014: Derlemeleri CLSCompliantAttribute ile işaretleme
|||
|-|-|
|TypeName|MarkAssembliesWithClsCompliant|
|CheckId|CA1014|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Bir derlemeyi yok <xref:System.CLSCompliantAttribute?displayProperty=fullName> özniteliğinin.

## <a name="rule-description"></a>Kural Tanımı
 Ortak Dil Tanımlaması (CLS) ad kısıtlamalarını, veri türlerini ve karşıt programlama dillerini kullanırsa derlemelerin uyması zorunlu olan kuralları tanımlar. İyi tasarım belirleyen tüm derlemeler ile CLS uyumluluğu açıkça belirtmek <xref:System.CLSCompliantAttribute>. Öznitelik bir derlemeye mevcut değilse, derleme uyumlu değil.

 Türlerini içeren veya uyumlu olmayan üyeler yazın CLS uyumlu bir derleme için mümkündür.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için derlemeye özniteliğini ekleyin. Tüm derleme uyumsuz olarak işaretleme yerine, hangi tür veya tür üyeleri uyumlu değildir ve bu nedenle bu öğeleri işaretleyin belirlemeniz gerekir. Mümkünse, geniş olası hedef kitle derlemenizi tüm işlevselliğini erişebilmesi için uyumsuz üyeleri için CLS uyumlu alternatifi sağlamalıdır.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın. Derleme uyumlu olmasını istemiyorsanız özniteliğini uygulayın ve değerini ayarlama `false`.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bir derlemeye gösterir <xref:System.CLSCompliantAttribute?displayProperty=fullName> uygulanan öznitelik, CLS uyumlu bildirir.

 [!code-csharp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CSharp/ca1014-mark-assemblies-with-clscompliantattribute_1.cs)]
 [!code-cpp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CPP/ca1014-mark-assemblies-with-clscompliantattribute_1.cpp)]
 [!code-vb[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/VisualBasic/ca1014-mark-assemblies-with-clscompliantattribute_1.vb)]

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.CLSCompliantAttribute?displayProperty=fullName> [Dil bağımsızlığı ve dilden bağımsız bileşenler](/dotnet/standard/language-independence-and-language-independent-components)