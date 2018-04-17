---
title: 'CA2147: Saydam yöntemler güvenlik kullanamazsınız onaylar | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- SecurityTransparentCodeShouldNotAssert
- CA2147
- CA2128
helpviewer_keywords:
- CA2128
- SecurityTransparentCodeShouldNotAssert
ms.assetid: 5d31e940-e599-4b23-9b28-1c336f8d910e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 75d841da0c738ff7504e95b372ecd4e06f9c77f2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2147-transparent-methods-may-not-use-security-asserts"></a>CA2147: Saydam türler güvenlik bildirimlerini kullanmamalıdır
|||  
|-|-|  
|TypeName|SecurityTransparentCodeShouldNotAssert|  
|CheckId|CA2147|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Olarak işaretlenmiş kod <xref:System.Security.SecurityTransparentAttribute> assert için yeterli izni verilmemiştir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural tüm yöntemleri ve ya da % 100 saydam veya karma saydam/kritik öneme sahiptir ve tüm bildirim temelli veya kesinlik temelli kullanımını bayrakları derlemedeki türleri çözümler <xref:System.Security.CodeAccessPermission.Assert%2A>.  
  
 Çalışma zamanında, yapılan her çağrı <xref:System.Security.CodeAccessPermission.Assert%2A> saydam koddan neden olacak bir <xref:System.InvalidOperationException> oluşturulmasına. Bu, her iki % 100 saydam derlemelerde ve burada bir metot veya tür saydam bildirilmiş ancak bildirim temelli veya kesinlik temelli Assert içerir karma saydam/kritik derlemelerde ortaya çıkabilir.  
  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 2.0 sunulan adlı bir özellik *saydamlık*. Tek tek yöntemleri, alanları, arabirimler, sınıfları ve türleri saydam ya da kritik olabilir.  
  
 Saydam kod güvenlik ayrıcalıkları yükseltmek için izin verilmiyor. Bu nedenle, tüm izinleri verilir veya bu talep çağıran veya ana bilgisayar uygulama etki alanına otomatik olarak kod üzerinden geçirilir. Yükseltmeleri örnekleri arasında Asserts, LinkDemands, SuppressUnmanagedCode, ve `unsafe` kodu.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Sorunu çözmek için ile Assert çağıran kodu ya da işaretlemek <xref:System.Security.SecurityCriticalAttribute>, veya Assert kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural gelen iletiyi bastırmak değil.  
  
## <a name="example"></a>Örnek  
 Bu kod başarısız olur `SecurityTestClass` saydam olduğunda `Assert` yöntemi atar bir <xref:System.InvalidOperationException>.  
  
 [!code-csharp[FxCop.Security.CA2147.TransparentMethodsMustNotUseSecurityAsserts#1](../code-quality/codesnippet/CSharp/ca2147-transparent-methods-may-not-use-security-asserts_1.cs)]  
  
## <a name="example"></a>Örnek  
 Bir seçenek üzere kod gözden geçirme SecurityTransparentMethod yöntemi aşağıdaki örnekte ve yöntemi yükseltme için güvenli olarak değerlendirilir, SecurityTransparentMethod işaretlemek ile güvenli kritik bu gerektiren ayrıntılı, tam ve hatasız güvenlik Denetim yöntemine bir çağrı-yöntemi Assert altında içinde gerçekleşen aşımı ayarlarına birlikte gerçekleştirilmelidir:  
  
 [!code-csharp[FxCop.Security.SecurityTransparentCode2#1](../code-quality/codesnippet/CSharp/ca2147-transparent-methods-may-not-use-security-asserts_2.cs)]  
  
 Assert koddan kaldırmak ve herhangi bir sonraki dosya Itanium tabanlı sistemler için g/ç izni taleplerin akışı SecurityTransparentMethod ötesinde çağırana izin vermek için ise başka bir seçenektir. Bu, güvenlik denetimleri sağlar. İzni taleplerini çağıran ve/veya uygulama etki alanı akar bu durumda, hiçbir güvenlik denetim genellikle yeterli olur. İzni taleplerini yakından barındırma ortamı ve kod kaynağı izin verir, güvenlik ilkesi aracılığıyla denetlenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenlik Uyarıları](../code-quality/security-warnings.md)