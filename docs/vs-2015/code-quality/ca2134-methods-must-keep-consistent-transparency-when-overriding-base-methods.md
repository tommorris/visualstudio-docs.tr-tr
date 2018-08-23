---
title: 'CA2134: Yöntemler tutarlı saydamlığı taban yöntemleri geçersiz kılarken tutmalıdır | Microsoft Docs'
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
- CA2134
ms.assetid: 3b17e487-0326-442e-90e1-dc0ba9cdd3f2
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: d803a0d8f75d216115fe11aa7b24475b775a5db8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632727"
---
# <a name="ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods"></a>CA2134: Yöntemler taban yöntemleri geçersiz kılarken tutarlı saydamlığı tutmalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2134: yöntemler taban yöntemleri geçersiz kılarken tutarlı saydamlığı tutması gerekir](https://docs.microsoft.com/visualstudio/code-quality/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods).  
  
TypeName | MethodsMustOverrideWithConsistentTransparency |  
| Checkıd | CA2134 |  
| Kategori | Microsoft.Security|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Bu kural bir yöntem ile işaretlendiğinde tetikler <xref:System.Security.SecurityCriticalAttribute> saydam veya ile işaretlenmiş bir yöntemi geçersiz kılmalar <xref:System.Security.SecuritySafeCriticalAttribute>. Kural, saydam veya ile işaretlenmiş bir yöntemi, harekete <xref:System.Security.SecuritySafeCriticalAttribute> ile işaretlenmiş yöntemi geçersiz bir <xref:System.Security.SecurityCriticalAttribute>.  
  
 Bu kural, sanal bir yöntemi geçersiz kılarken veya bir arabirim uygulanırken uygulanır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural bir yöntem daha devralım zincirinde yukarı doğru güvenlik erişilebilirliğini girişimleri tetikler. Taban sınıfında sanal bir yöntem, saydam veya güvenli kritik ise, örneğin, ardından türetilmiş sınıf, saydam veya güvenli kritik bir yöntemle geçersiz kılmanız gerekir. Sanal güvenlik açısından kritik ise, buna karşılık, türetilmiş sınıf, bir güvenlik kritik yöntemi geçersiz kılmanız gerekir. Aynı kural, arabirim yöntemleri uygulamak için geçerlidir.  
  
 Saydamlık kuralları saydamlık hesaplama dinamik tür bilgisi yok. böylece kodu yerine çalışma zamanında derlenmiş JIT olduğunda uygulanır. Bu nedenle, saydamlık hesaplama sonucu olan JIT olarak derlenmiş dinamik türden bağımsız olarak, yalnızca statik türlerinden belirlenemedi olmalıdır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için sanal yöntemini geçersiz kılma veya sanal saydamlık ya da arabirim yöntemi eşleştirmek için bir arabirimi uygulayan yöntem saydamlığını değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıları bastırmayın. Bu kural ihlalleri çalışma zamanı'nda neden <xref:System.TypeLoadException> Düzey 2 Asetatını kullanın derlemeler için.  
  
## <a name="examples"></a>Örnekler  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Security.CA2134.MethodsMustOverrideWithConsistentTransparency#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2134.methodsmustoverridewithconsistenttransparency/cs/ca2134 - methodsmustoverridewithconsistenttransparency.cs#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenliği saydam kod, Düzey 2](http://msdn.microsoft.com/library/4d05610a-0da6-4f08-acea-d54c9d6143c0)



