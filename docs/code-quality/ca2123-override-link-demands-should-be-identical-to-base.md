---
title: 'CA2123: Geçersiz kılma bağlantı talepleri taban ile özdeş olmalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2123
- OverrideLinkDemandsShouldBeIdenticalToBase
helpviewer_keywords:
- OverrideLinkDemandsShouldBeIdenticalToBase
- CA2123
ms.assetid: 4538ecd5-fc6f-4480-ab00-90b2ce4730db
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9c23bdf9246855fc4a91d5cd5f748f8f8fb17a67
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2123-override-link-demands-should-be-identical-to-base"></a>CA2123: Geçersiz kılan bağlantı talepleri taban ile özdeş olmalıdır
|||  
|-|-|  
|TypeName|OverrideLinkDemandsShouldBeIdenticalToBase|  
|CheckId|CA2123|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Ortak tür genel ya da korumalı yönteminde bir yöntemini geçersiz kılar veya bir arabirimini uygulayan ve aynı yok [bağlantı talepleri](/dotnet/framework/misc/link-demands) arabirimi ya da sanal bir yöntem olarak.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural, arabirim ya da başka bir türdeki sanal yöntem olan temel yöntem ile başka bir yöntemi eşleştirir ve sonra her bir bağlantı talebini inceler. Bir ihlali yöntemi ya da temel yöntemi bir bağlantı isteği varsa ve diğer yok bildirilir.  
  
 Bu kural ihlal edilirse, kötü amaçlı çağıran yalnızca güvenli olmayan yöntemini çağırarak bağlantı isteği atlayabilirsiniz.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için aynı bağlantı isteği geçersiz kılma yöntemi veya uygulama için geçerlidir. Bu mümkün değilse, tam bir isteğe bağlı yöntemiyle işaretlemek veya öznitelik tamamen kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu kural çeşitli ihlalleri gösterir.  
  
 [!code-csharp[FxCop.Security.OverridesAndSecurity#1](../code-quality/codesnippet/CSharp/ca2123-override-link-demands-should-be-identical-to-base_1.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenli kodlama yönergeleri](/dotnet/standard/security/secure-coding-guidelines)   
 [Bağlantı talepleri](/dotnet/framework/misc/link-demands)