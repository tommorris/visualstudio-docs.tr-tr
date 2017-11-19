---
title: "CA2104: Okuma yalnızca kesilebilir başvuru türleri bildirmeyin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotDeclareReadOnlyMutableReferenceTypes
- CA2104
helpviewer_keywords:
- CA2104
- DoNotDeclareReadOnlyMutableReferenceTypes
ms.assetid: 81b83ee5-4db5-4be0-9f8d-90b53894ec3b
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5691abd58801d3be6a543a72b5a1f4ca209d3a17
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2104-do-not-declare-read-only-mutable-reference-types"></a>CA2104: Salt okunur kesilebilir başvuru türleri bildirmeyin
|||  
|-|-|  
|TypeName|DoNotDeclareReadOnlyMutableReferenceTypes|  
|CheckId|CA2104|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Dışarıdan görünen bir tür, kesilebilir başvuru türü olan dışarıdan görünen bir salt okunur alan içerir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Kesilebilir tür, örnek verileri değiştirilebilen bir türdür. <xref:System.Text.StringBuilder?displayProperty=fullName> Sınıfı kesilebilir başvuru türünde bir örnek verilmiştir. Sınıfının bir örneği değerini değiştirebilir üye içeriyor. Bir sabit başvuru türü örneğidir <xref:System.String?displayProperty=fullName> sınıfı. Örneği oluşturulduktan sonra değeri hiçbir zaman değiştirebilirsiniz.  
  
 Salt okunur değiştiricisi ([readonly](/dotnet/csharp/language-reference/keywords/readonly) C# ' ta, [ReadOnly](/dotnet/visual-basic/language-reference/modifiers/readonly) içinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], ve [const](/cpp/cpp/const-cpp) C++'ta) bir başvuru türü alan (c++ işaretçisi) alan engeller Başvuru türü farklı bir örneği tarafından değiştirildi. Ancak, değiştiricisi üzerinden başvuru türü değiştiren örnek veri alanının engellemez.  
  
 Salt okunur dizi alanları bu kuraldan muafiyet ancak bunun yerine ihlal neden [CA2105: dizi alanları okunamadığı için yalnızca](../code-quality/ca2105-array-fields-should-not-be-read-only.md) kuralı.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için salt okunur değiştiricisi kaldırın veya önemli bir değişiklik kabul edilebilir ise, alan bir değişmez tür ile değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Alan türü değişmez ise bir uyarı bu kuraldan gizlemek güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu kural ihlal neden olan bir alan bildiriminde gösterir.  
  
 [!code-cpp[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/CPP/ca2104-do-not-declare-read-only-mutable-reference-types_1.cpp)]
 [!code-csharp[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/CSharp/ca2104-do-not-declare-read-only-mutable-reference-types_1.cs)]
 [!code-vb[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/VisualBasic/ca2104-do-not-declare-read-only-mutable-reference-types_1.vb)]