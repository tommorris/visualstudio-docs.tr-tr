---
title: 'CA2222: devralınan üye görünürlüğünü azaltmayın | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DoNotDecreaseInheritedMemberVisibility
- CA2222
helpviewer_keywords:
- DoNotDecreaseInheritedMemberVisibility
- CA2222
ms.assetid: 066c8675-381f-43cc-956c-d757cc494028
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: e566750d5a1cdd5f2671e47c71de57ab479cc0dd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688543"
---
# <a name="ca2222-do-not-decrease-inherited-member-visibility"></a>CA2222: Devralınan üye görünürlüğünü azaltmayın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2222: devralınan üye görünürlüğünü azaltmayın](https://docs.microsoft.com/visualstudio/code-quality/ca2222-do-not-decrease-inherited-member-visibility).  
  
TypeName | DoNotDecreaseInheritedMemberVisibility |  
| Checkıd | CA2222 |  
| Kategori | Microsoft.Usage|  
| Yeni değişiklik | Olmayan yeni |  
  
## <a name="cause"></a>Sebep  
 Aynı temel türünde bildirilen bir genel yöntem imzası bir tür özel bir yöntem vardır. Özel yöntem son değil.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Devralınan üyeler için erişim değiştiricisini değiştirmemelisiniz. Devralınmış bir üyeyi özel olarak değiştirme, arayanların yöntemin temel sınıf uygulamasına erişmesini engellemez. Üye özel yapıldı ve korumasız bir türüdür, türler, devralmasına devralma hiyerarşisinde son genel yöntemin uygulanmasını çağırabilirsiniz. Erişim değiştiricisi değiştirmeniz gerekiyorsa, yöntemi son işaretlenmelidir veya yöntemi geçersiz kılınmasını önlemek için türü sealed olmalıdır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için özel olmayan erişimine değiştirin. Programlama diliniz destekliyorsa, alternatif olarak, yöntem son yapabilirsiniz.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bu kuralı ihlal eden bir tür gösterir.  
  
 [!code-csharp[FxCop.Usage.InheritedPublic#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.InheritedPublic/cs/FxCop.Usage.InheritedPublic.cs#1)]
 [!code-vb[FxCop.Usage.InheritedPublic#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.InheritedPublic/vb/FxCop.Usage.InheritedPublic.vb#1)]



