---
title: "Ca2106: bildirimlerin Güvenliğini onaylar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2106
- SecureAsserts
helpviewer_keywords:
- CA2106
- SecureAsserts
ms.assetid: 91feb36e-6e2c-436c-8272-5aee31f77e98
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 33e200b06ed9bb0999116ea91a64b06aaa879067
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2106-secure-asserts"></a>CA2106: Bildirimlerin güvenliğini sağlayın
|||  
|-|-|  
|TypeName|SecureAsserts|  
|CheckId|CA2106|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir yöntem izin ileri sürer ve güvenlik önlemi olmayan çağrı üzerinde gerçekleşir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Güvenlik denetimleri yapmadan herhangi bir güvenlik izni ileri sürmek, kodunuzdaki güvenlik zayıflıklarını yararlanılabilir bırakır. Bir güvenlik izni uygulanan güvenlik yığın ilerlemesi durdurur. Arayan üzerinde herhangi bir denetim yapmadan izin assert, çağıran dolaylı olarak kod izinlerinizi kullanarak yürütebilir. Yalnızca assert zararlı bir biçimde kullanıldığından emin olduğunuzda verilebilir güvenlik denetimlerini olmadan onaylar. Assert çağırmanız kodu zararsız ise zararsız veya kullanıcılar, çağıran kodu rasgele bilgi geçiremezsiniz.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için güvenlik talebi yöntemi veya bildiri türü ekleyin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan dikkatli güvenlik incelemesi sonra yalnızca engelleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>   
 [Güvenli Kodlama Yönergeleri](/dotnet/standard/security/secure-coding-guidelines)