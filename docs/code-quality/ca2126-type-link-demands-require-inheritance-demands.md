---
title: "CA2126: Tür bağlantı talepleri devralma taleplerini gerektirir. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
helpviewer_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
ms.assetid: 07b604e5-5579-4df9-a578-dadd0d8370a7
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 254fd15f97afe69f927bb8a1aae1954105776641
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2126-type-link-demands-require-inheritance-demands"></a>CA2126: Tür bağlantı talepleri devralma taleplerini gerektirir
|||  
|-|-|  
|TypeName|TypeLinkDemandsRequireInheritanceDemands|  
|CheckId|CA2126|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Ortak korumasız tür korumalı bir bağlantı isteği ile geçersiz kılınabilir bir yöntemi vardır ve türünün veya yöntemi ile bir devralma isteğe korunur.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir bağlantı isteği bir yöntem veya bildiri türü üzerinde belirtilen izninin anında arayanlar yönteminin gerektirir. Bir devralma isteğe bağlı bir yöntem olarak belirtilen izninizin olması için bir geçersiz kılma yöntemi gerektirir. Bir devralma isteğe bağlı bir türü olarak belirtilen izne sahip bir türetilen sınıf gerektirir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için türü veya yöntemi bir devralma isteğe bağlı bağlantı isteğe bağlı olarak aynı izni ile güvenli hale getirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kuralını ihlal eden bir tür gösterir.  
  
 [!code-cpp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CPP/ca2126-type-link-demands-require-inheritance-demands_1.cpp)]
 [!code-vb[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/VisualBasic/ca2126-type-link-demands-require-inheritance-demands_1.vb)]
 [!code-csharp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2126-type-link-demands-require-inheritance-demands_1.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2108: değer türleri üzerinde bildirimsel güvenliği gözden geçirin](../code-quality/ca2108-review-declarative-security-on-value-types.md)  
  
 [CA2112: Güvenli türler alanları açığa çıkarmamalıdır](../code-quality/ca2112-secured-types-should-not-expose-fields.md)  
  
 [CA2122: bağlantı talepleri olan yöntemleri dolaylı olarak gösterme](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)  
  
 [CA2123: Geçersiz kılma bağlantı talepleri taban ile özdeş olmalıdır](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenli kodlama yönergeleri](/dotnet/standard/security/secure-coding-guidelines)   
 [Devralma taleplerini](http://msdn.microsoft.com/en-us/28b9adbb-8f08-4f10-b856-dbf59eb932d9)   
 [Bağlantı talepleri](/dotnet/framework/misc/link-demands)   
 [Talepleri](http://msdn.microsoft.com/en-us/e5283e28-2366-4519-b27d-ef5c1ddc1f48)