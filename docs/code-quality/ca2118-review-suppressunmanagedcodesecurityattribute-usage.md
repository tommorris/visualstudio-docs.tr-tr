---
title: 'CA2118: SuppressUnmanagedCodeSecurityAttribute kullanımını gözden geçir'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2118
- ReviewSuppressUnmanagedCodeSecurityUsage
helpviewer_keywords:
- ReviewSuppressUnmanagedCodeSecurityUsage
- CA2118
ms.assetid: 4cb8d2fc-4e44-4dc3-9b74-7f5838827d41
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 3eeff4eca5bcc6d2490fc077501726e3ba7e8de1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2118-review-suppressunmanagedcodesecurityattribute-usage"></a>CA2118: SuppressUnmanagedCodeSecurityAttribute kullanımını gözden geçir
|||
|-|-|
|TypeName|ReviewSuppressUnmanagedCodeSecurityUsage|
|CheckId|CA2118|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Genel veya korumalı tür veya üye olan <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> özniteliği.

## <a name="rule-description"></a>Kural Tanımı
 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> COM birlikte çalışma veya platform çağırma kullanma yönetilmeyen kod yürütmek için üyeleri için varsayılan güvenlik sistem davranışını değiştirir. Genellikle, sistem yapar bir [veri ve modelleme](/dotnet/framework/data/index) yönetilmeyen kod izni. Bu isteğe bağlı üye her çalıştırılışı için çalışma zamanında gerçekleşir ve her çağıran çağrı yığınında izin denetler. Öznitelik mevcut olduğunda, sistemin yapar bir [bağlantı talepleri](/dotnet/framework/misc/link-demands) izni: arayan JIT derlenmiş olduğunda anında arayanlar izinleriyle denetlenir.

 Bu öznitelik, öncelikle performansı artırmak için kullanılır; ancak, gelen performans artışı önemli güvenlik riskleri ile gelir. Yerel yöntemlerini çağıran ortak üye öznitelik yerleştirirseniz (dışında anında arayanlar) çağrı yığınında arayanlar yönetilmeyen kod yönetilmeyen kod yürütme izni gerekmez. Ortak üyenin eylemleri ve giriş işleme bağlı olarak, normalde güvenilir kodu kısıtlı erişim işlevselliği güvenilmez arayanlara izin verebilir.

 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Arayanlar doğrudan geçerli işlemin adres alanı erişmesini engellemek için güvenlik denetimlerini kullanır. Bu öznitelik normal güvenlik atladığından okumak veya yazmak için işlemin bellek için kullanılabiliyorsa, kodunuzun bir ciddi tehdidi. Risk bilerek bellek işlemek için erişim sağlayan yöntemler için sınırlı olduğunu unutmayın; Burada kötü amaçlı kod erişim herhangi bir yolla, örneğin, şaşırtıcı, hatalı biçimlendirilmiş veya geçersiz giriş sağlayarak elde edebilirsiniz herhangi bir senaryoda de mevcuttur.

 Yerel bilgisayardan yürütüyor veya aşağıdaki gruplardan birinin üyesi olduğu sürece varsayılan güvenlik ilkesi bir derlemeye yönetilmeyen kod izin vermez:

-   Bilgisayar bölge kodu grubum

-   Microsoft Güçlü ad kod grubu

-   ECMA tanımlayıcı adı kod grubu

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu öznitelik kesinlikle gerekli olduğundan emin olmak için kodunuzu dikkatle gözden geçirin. Yönetilen kod güvenlik ile ilgili bilginiz ya da bu özniteliği kullanılarak güvenlik etkilerini anlaşılmıyor kodunuzdan kaldırın. Öznitelik gerekiyorsa, arayanlar kodunuzu amaçla kullanamazsınız emin olmalısınız. Kodunuzu yönetilmeyen kod yürütmek için izni yok, bu öznitelik herhangi bir etkisi olmaz ve kaldırılması gerekir.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural bir uyarıdan güvenle gizlemek için kodunuzu arayanlar yerel operations veya zararlı bir şekilde kullanılabilir kaynaklara erişim sağlamaz emin olmalısınız.

## <a name="example"></a>Örnek
 Aşağıdaki örnek kural ihlal ediyor.

 [!code-csharp[FxCop.Security.TypesDoNotSuppress#1](../code-quality/codesnippet/CSharp/ca2118-review-suppressunmanagedcodesecurityattribute-usage_1.cs)]

## <a name="example"></a>Örnek
 Aşağıdaki örnekte, `DoWork` yöntemi sağlar platform çağırma yöntemi için bir genel olarak erişilebilir kod yolu `FormatHardDisk`.

 [!code-csharp[FxCop.Security.PInvokeAndSuppress#1](../code-quality/codesnippet/CSharp/ca2118-review-suppressunmanagedcodesecurityattribute-usage_2.cs)]

## <a name="example"></a>Örnek
 Aşağıdaki örnekte, genel yöntem `DoDangerousThing` bir ihlaline neden olur. İhlali çözümlemek için `DoDangerousThing` özel yapılmalıdır ve erişimi olmalıdır güvenlik isteğe bağlı güvenli bir genel yöntem aracılığıyla tarafından gösterildiği gibi `DoWork` yöntemi.

 [!code-csharp[FxCop.Security.TypeInvokeAndSuppress#1](../code-quality/codesnippet/CSharp/ca2118-review-suppressunmanagedcodesecurityattribute-usage_3.cs)]

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> [Güvenli kodlama yönergeleri](/dotnet/standard/security/secure-coding-guidelines) [veri ve modelleme](/dotnet/framework/data/index) [bağlantı talepleri](/dotnet/framework/misc/link-demands)
