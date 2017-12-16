---
title: "CA1014: Derlemeleri CLSCompliantAttribute işaretlemek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
helpviewer_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
ms.assetid: 4fe57449-cf45-4745-bcd2-6345f1ed266d
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 44ce0dc31fc8e1d9acd2a2f93ca53fd1aeca3ee9
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/12/2017
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
 <xref:System.CLSCompliantAttribute?displayProperty=fullName>   
 [Dil Bağımsızlığı ve Dilden Bağımsız Bileşenler](/dotnet/standard/language-independence-and-language-independent-components)