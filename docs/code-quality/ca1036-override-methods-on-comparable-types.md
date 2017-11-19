---
title: "CA1036: Karşılaştırılabilir türlerde yöntemleri geçersiz kılmak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1036
- OverrideMethodsOnComparableTypes
helpviewer_keywords:
- OverrideMethodsOnComparableTypes
- CA1036
ms.assetid: 2329f844-4cb8-426d-bee2-cd065d1346d0
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d07e63363542a9bf5a1dd756026183349659abe1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1036-override-methods-on-comparable-types"></a>CA1036: Karşılaştırılabilir türlerde geçersiz kılma yöntemleri
|||  
|-|-|  
|TypeName|OverrideMethodsOnComparableTypes|  
|CheckId|CA1036|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir genel ya da korumalı türü uygulayan <xref:System.IComparable?displayProperty=fullName> arabirim ve geçersiz <xref:System.Object.Equals%2A?displayProperty=fullName> veya eşitliği, eşitsizlik, daha küçük veya büyük dile özgü işleci aşırı değil. Kural türü yalnızca arabirimi uygulaması devralıyorsa ihlalinin raporlamaz.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Özel bir sıralama düzeni tanımlamak türleri uygulayan <xref:System.IComparable> arabirimi. <xref:System.IComparable.CompareTo%2A> Yöntemi türü iki örneği için doğru sıralama düzenini belirten bir tamsayı değeri döndürür. Bu kural bir sıralama düzeni ayarlamak türlerini tanımlar; Bu eşitlik, eşitsizlik, olağan anlamını daha az daha küçük ve büyük geçerli olduğunu gösterir. Uygulaması sağladığınız zaman <xref:System.IComparable>, genellikle gerekir ayrıca geçersiz <xref:System.Object.Equals%2A> böylece tutarlı olan değerler döndürür <xref:System.IComparable.CompareTo%2A>. Geçersiz kılarsanız <xref:System.Object.Equals%2A> ve kodlama olan işlecin destekleyen bir dilde tutarlı olan işleçleri de sağlamalıdır <xref:System.Object.Equals%2A>.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için geçersiz kılma <xref:System.Object.Equals%2A>. İşleç aşırı yüklemesi programlama diliniz destekliyorsa, aşağıdaki işleçleri sağlayın:  
  
-   op_Equality  
  
-   op_Inequality  
  
-   op_LessThan  
  
-   op_GreaterThan  
  
 C# ' ta bu işleçlere temsil etmek için kullanılan belirteç şu şekildedir: ==,! =, \<, ve >.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Visual Basic .NET ile olduğu gibi programlama diliniz İşleç aşırı yüklemesi, desteklemez ve eksik işleçleri tarafından ihlaline neden olduğunda bir uyarı bu kuraldan bastırmak güvenlidir. İşleçler uygulayan karar verirseniz op_Equality uygulama bağlamında anlamsız dışında eşitlik işleçleri başlatıldığında bu kural için bir uyarı gizlemek güvenlidir. Her zaman ancak op_Equality gerekir ve Object.Equals geçersiz kılarsanız == işleci.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, doğru uygulayan bir tür içerir <xref:System.IComparable>. Kod açıklamaları tanımlamak için ilgili çeşitli kurallarını karşılayan yöntemleri <xref:System.Object.Equals%2A> ve <xref:System.IComparable> arabirimi.  
  
 [!code-csharp[FxCop.Design.IComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_1.cs)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki uygulama davranışını testleri <xref:System.IComparable> daha önce gösterilen uygulama.  
  
 [!code-csharp[FxCop.Design.TestIComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_2.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.IComparable?displayProperty=fullName>   
 <xref:System.Object.Equals%2A?displayProperty=fullName>   
 [Eşitlik işleçleri](/dotnet/standard/design-guidelines/equality-operators)