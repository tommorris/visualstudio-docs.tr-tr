---
title: 'CA2131: Güvenlik kritik türleri tür eşdeğerliğine katılamaz | Microsoft Docs'
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
- CA2131
ms.assetid: 4170f3b1-6086-430d-8fba-837d5538c573
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: dc9e166d65636f748f53c8ee896f858c55a94076
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691022"
---
# <a name="ca2131-security-critical-types-may-not-participate-in-type-equivalence"></a>CA2131: Güvenlik kritik türleri tür eşdeğerliğine katılamaz
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2131: güvenlik kritik türleri tür eşdeğerliğine katılmak](https://docs.microsoft.com/visualstudio/code-quality/ca2131-security-critical-types-may-not-participate-in-type-equivalence).  
  
TypeName | CriticalTypesMustNotParticipateInTypeEquivalence |  
| Checkıd | CA2131 |  
| Kategori | Microsoft.Security|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Tür eşdeğerliği ve bir ya da türün kendisine bir tür katıldığı veya bir üye veya alan türü ile işaretlenmiş <xref:System.Security.SecurityCriticalAttribute> özniteliği.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural, herhangi kritik türler veya kritik yöntemleri içeren türler veya tür eşdeğerliğine katılan alanlar tetiklendiğinde başlatılır. CLR böyle bir türü algıladığında, ile yüklemek başarısız bir <xref:System.TypeLoadException> çalışma zamanında. Tipik olarak bu kural, kullanıcılar tlbimp'e güvenmek yerine el ile tür eşdeğerliği uyguladığında başlar ve derleyiciler tür eşdeğerliği yapar.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için SecurityCritical özniteliği kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekler, bir arabirim, bir yöntem ve bu kural ateşlenmesine neden olacak bir alanı göstermektedir.  
  
 [!code-csharp[FxCop.Security.CA2131.CriticalTypesMustNotParticipateInTypeEquivalence#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2131.criticaltypesmustnotparticipateintypeequivalence/cs/ca2131 - criticaltypesmustnotparticipateintypeequivalence.cs#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenliği saydam kod, Düzey 2](http://msdn.microsoft.com/library/4d05610a-0da6-4f08-acea-d54c9d6143c0)



