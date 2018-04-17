---
title: 'CA2107: Gözden geçirmeyi Reddet ve yalnızca kullanımına izin ver | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2107
- ReviewDenyAndPermitOnlyUsage
helpviewer_keywords:
- ReviewDenyAndPermitOnlyUsage
- CA2107
ms.assetid: 366f4a56-ae93-4882-81d0-bd0a55ebbc26
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e1d8eb2b3cda2684dbae218d10abc7594b6f5f55
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2107-review-deny-and-permit-only-usage"></a>CA2107: Gözden geçirmeyi reddet ve yalnızca kullanımına izin ver
|||  
|-|-|  
|TypeName|ReviewDenyAndPermitOnlyUsage|  
|CheckId|CA2107|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir yöntem PermitOnly veya reddetme güvenlik eylemi belirtir. bir güvenlik denetimi içerir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 <xref:System.Security.CodeAccessPermission.Deny%2A?displayProperty=fullName> Güvenlik eylemi yalnızca Gelişmiş bilgisine sahip olan bu tarafından kullanılmalıdır, [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] güvenlik. Bu güvenlik eylemlerini kullanan kod güvenlik incelemesi altından geçmelidir.  
  
 Reddetme güvenlik talebi karşılamak üzere oluşur yığın ilerlemesi varsayılan davranışını değiştirir. Çağrı yığınında arayanlar, gerçek izinlerinden bağımsız olarak reddeden yöntemi süresince verilmelidir değil izinleri belirtmenize olanak sağlar. Yığın ilerlemesi reddetme tarafından güvenli hale getirilmiş bir yöntem algılar ve istenilen izni reddedildi izinler eklediyseniz yığın ilerlemesi başarısız olursa. PermitOnly de yığın ilerlemesi varsayılan davranışını değiştirir. Arayanlar izinlere bakılmaksızın verilebilecek izinleri belirlemek kod sağlar. Yığın ilerlemesi PermitOnly tarafından güvenli hale getirilmiş bir yöntem algılar ve istenilen izni PermitOnly tarafından belirtilen izinleri dahil edilmezse, yığın ilerlemesi başarısız olursa.  
  
 Bu eylemler dayanır kodu kendi sınırlı yararlılığını ve zarif davranışı nedeniyle güvenlik açıklarını dikkatlice değerlendirilmelidir. Aşağıdakileri göz önünde bulundurun:  
  
-   [Bağlantı talepleri](/dotnet/framework/misc/link-demands) izin verme veya PermitOnly tarafından etkilenmez.  
  
-   Yığın ilerlemesi neden olan isteğe bağlı olarak aynı yığın çerçevesinde izin verme veya PermitOnly meydana gelirse, güvenlik eylemlerini bir etkisi yoktur.  
  
-   Yol tabanlı izinler oluşturmak için kullanılan değerler genellikle birden çok yolla belirtilebilir. Yolun bir form erişimi reddetme tüm formları erişimini değil. Örneğin, bir dosya paylaşımı, \\\Server\Share bir ağ sürücüsü paylaşımdaki bir dosyaya erişimi engellemek için X: eşleştirilir, reddetme gerekir \\\Server\Share\File, X:\File ve dosyayı erişen her bir yol.  
  
-   Bir <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName> izin verme veya PermitOnly ulaşılmadan önce yığın ilerlemesi sonlandırabilir.  
  
-   Reddetme herhangi bir etkisi varsa, çağıran reddetme tarafından engelleniyor izninin zaman öğesine, çağıran korumalı kaynağa doğrudan reddetme atlayarak erişebilirsiniz. Benzer şekilde, çağıran reddedilen izni yoksa, yığın ilerlemesi reddetme başarısız olur.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu güvenlik eylemleri herhangi bir kullanımından bir ihlali neden olur. Bir ihlali düzeltmek için bu güvenlik eylemleri kullanmayın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Yalnızca güvenlik incelemesi tamamladıktan sonra bu kural bir uyarıdan engelleyin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, reddetme bazı sınırlamaları gösterir.  
  
 Aşağıdaki kitaplığı onları korumak güvenlik taleplerini dışında birbirinin aynı olan iki yöntem olan bir sınıfı içerir.  
  
 [!code-csharp[FxCop.Security.PermitAndDeny#1](../code-quality/codesnippet/CSharp/ca2107-review-deny-and-permit-only-usage_1.cs)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki uygulama Kitaplığı'ndan reddetme etkilerini güvenli yöntemleri gösterir.  
  
 [!code-csharp[FxCop.Security.TestPermitAndDeny#1](../code-quality/codesnippet/CSharp/ca2107-review-deny-and-permit-only-usage_2.cs)]  
  
 Bu örnek şu çıkışı üretir.  
  
 **İsteğe bağlı: Arayanın reddetme isteğe bağlı sürülen izni olan etkisi yoktur.**  
**LinkDemand: Arayanın reddetme LinkDemand sürülen izni olan etkisi yoktur.**  
**LinkDemand: Arayanın reddetme LinkDemand korumalı kod ile herhangi bir etkisi olmaz.**  
**LinkDemand: Bu reddetme LinkDemand korumalı kod ile herhangi bir etkisi olmaz.**   
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Security.CodeAccessPermission.PermitOnly%2A?displayProperty=fullName>   
 <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>   
 <xref:System.Security.CodeAccessPermission.Deny%2A?displayProperty=fullName>   
 <xref:System.Security.IStackWalk.PermitOnly%2A?displayProperty=fullName>   
 [Güvenli Kodlama Yönergeleri](/dotnet/standard/security/secure-coding-guidelines)   

