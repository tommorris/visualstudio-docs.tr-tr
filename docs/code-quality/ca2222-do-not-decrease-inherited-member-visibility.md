---
title: 'CA2222: Devralınan üye görünürlüğünü azaltmayın'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
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
ms.openlocfilehash: fa8730789ef9f905def64c17081eb44113241282
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
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