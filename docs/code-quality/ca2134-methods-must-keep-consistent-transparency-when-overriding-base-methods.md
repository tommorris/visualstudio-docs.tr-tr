---
title: "CA2134: Yöntemler tutarlı saydamlığı taban yöntemleri geçersiz kılarken tutmalısınız | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CA2134
ms.assetid: 3b17e487-0326-442e-90e1-dc0ba9cdd3f2
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: feb33e630322237522c98ff3f803bc44b3fbcc86
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods"></a>CA2134: Yöntemler taban yöntemleri geçersiz kılarken tutarlı saydamlığı tutmalıdır
|||  
|-|-|  
|TypeName|MethodsMustOverrideWithConsistentTransparency|  
|CheckId|CA2134|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bu kural bir yöntem ile işaretlendiğinde harekete <xref:System.Security.SecurityCriticalAttribute> saydam veya ile işaretli bir yöntem geçersiz kılmaları <xref:System.Security.SecuritySafeCriticalAttribute>. Saydam veya ile işaretli bir yöntem, kural da ateşlenir <xref:System.Security.SecuritySafeCriticalAttribute> ile işaretli bir yöntem geçersiz kılan bir <xref:System.Security.SecurityCriticalAttribute>.  
  
 Bu kural, sanal bir yöntemi geçersiz kılarken veya bir arabirim uygulanırken uygulanır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural bir yöntemi daha fazla devralma zincirini güvenlik erişilebilirliğini değiştirme girişimleri üzerinde ateşlenir. Saydam veya güvenli kritik bir taban sınıf içinde sanal bir yöntem ise, örneğin, ardından türetilmiş sınıf onu saydam veya güvenli kritik yöntemiyle geçersiz kılmanız gerekir. Sanal güvenlik açısından kritik ise, buna karşılık, türetilmiş sınıf, bir güvenlik kritik yöntemi ile geçersiz kılmanız gerekir. Aynı kural arabirim yöntemleri uygulamak için geçerlidir.  
  
 Böylece saydamlık hesaplama dinamik tür bilgileri yok kodu yerine çalışma zamanında derlenen JIT olduğunda saydamlık kurallar zorlanır. Bu nedenle, saydamlık hesaplamanın sonucu yalnızca JIT-derlenmiş dinamik türü ne olursa olsun, olan statik türlerinden belirlenemedi olmalıdır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için sanal bir yöntem geçersiz kılma veya sanal saydamlığını veya arabirim yöntemi eşleşecek şekilde arabirimi uygulama yöntemi saydamlığını değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıları bastırma değil. Bu kural ihlalleri, çalışma zamanı'nda sonuçlanacak <xref:System.TypeLoadException> Düzey 2 saydamlık kullanmak derlemeler için.  
  
## <a name="examples"></a>Örnekler  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Security.CA2134.MethodsMustOverrideWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods_1.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenliği saydam kod, Düzey 2](http://msdn.microsoft.com/Library/4d05610a-0da6-4f08-acea-d54c9d6143c0)