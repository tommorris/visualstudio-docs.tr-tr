---
title: "CA1034: İç içe geçmiş türler görünebilir olmamalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
helpviewer_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
ms.assetid: e9789a2c-2540-42a1-8705-ae7104011194
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: dc35514eab2344c086305ec88435ff8a32285e4f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1034-nested-types-should-not-be-visible"></a>CA1034: İç içe türler görünebilir olmamalıdır
|||  
|-|-|  
|TypeName|NestedTypesShouldNotBeVisible|  
|CheckId|CA1034|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir harici olarak görünebilir tür bir harici olarak görünen türü bildirimi içerir. İç içe geçmiş numaralandırmalar ve korumalı türleri bu kuraldan dışındadır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Başka bir tür kapsamı içinde bildirilen bir türü bir iç içe geçmiş türüdür. İç içe geçmiş türler, kapsayan tür özel uygulama ayrıntılarını kapsüllemek için kullanışlıdır. Bu amaçla kullanılan, iç içe türün dışarıdan görünür olmaması gerekir.  
  
 Dışarıdan görünür iç içe geçmiş türler mantıksal gruplandırma için veya ad çakışmaları önlemek için kullanmayın; Bunun yerine, ad alanları kullanın.  
  
 İç içe geçmiş türler bazı programcıları açıkça anlaşılmıyor üye erişilebilirlik kavramı içerir.  
  
 Alt sınıfların ve iç içe geçmiş türler öncelikli özelleştirme senaryolarında korumalı türleri kullanılabilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Harici olarak görünür olmasını iç içe geçmiş tür düşünmüyorsanız tür erişilebilirlik değiştirin. Aksi takdirde, iç içe geçmiş tür üst öğesinden kaldırın. İç içe geçme amacı, iç içe geçmiş tür kategorilere ayırmak için ise, hiyerarşi yerine oluşturmak için bir ad kullanın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kuralını ihlal eden bir tür gösterir.  
  
 [!code-cpp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CPP/ca1034-nested-types-should-not-be-visible_1.cpp)]
 [!code-csharp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CSharp/ca1034-nested-types-should-not-be-visible_1.cs)]
 [!code-vb[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/VisualBasic/ca1034-nested-types-should-not-be-visible_1.vb)]