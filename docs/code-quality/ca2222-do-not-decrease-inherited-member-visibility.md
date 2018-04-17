---
title: 'CA2222: devralınan üye görünürlüğünü azaltmayın | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- DoNotDecreaseInheritedMemberVisibility
- CA2222
helpviewer_keywords:
- DoNotDecreaseInheritedMemberVisibility
- CA2222
ms.assetid: 066c8675-381f-43cc-956c-d757cc494028
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: de96b199adf5b282f70207478e4d9ae38c4d00f5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2222-do-not-decrease-inherited-member-visibility"></a>CA2222: Devralınan üye görünürlüğünü azaltmayın
|||  
|-|-|  
|TypeName|DoNotDecreaseInheritedMemberVisibility|  
|CheckId|CA2222|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Korumasız bir tür özel bir yöntem bir taban türü bildirilmiş bir ortak yöntemi aynıdır bir imza içeriyor. Özel yöntem son değil.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Devralınan üyeler için erişim değiştiricisini değiştirmemelisiniz. Devralınmış bir üyeyi özel olarak değiştirme, arayanların yöntemin temel sınıf uygulamasına erişmesini engellemez. Üye özel yapılır ve türü korumasız ise, türleri devralma devralma hiyerarşisinde yöntemi son ortak uyarlamasını çağırabilirsiniz. Erişim değiştiricisi değiştirmeniz gerekiyorsa yöntemi son olarak işaretlenmelidir veya türünü yöntemi geçersiz kılınmasını önlemek için korumalı olmalıdır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için özel olmayan erişimine değiştirin. Programlama diliniz destekliyorsa, alternatif olarak, yöntem son duruma getirebilirsiniz.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu kural ihlal eden bir tür gösterir.  
  
 [!code-vb[FxCop.Usage.InheritedPublic#1](../code-quality/codesnippet/VisualBasic/ca2222-do-not-decrease-inherited-member-visibility_1.vb)]
 [!code-csharp[FxCop.Usage.InheritedPublic#1](../code-quality/codesnippet/CSharp/ca2222-do-not-decrease-inherited-member-visibility_1.cs)]