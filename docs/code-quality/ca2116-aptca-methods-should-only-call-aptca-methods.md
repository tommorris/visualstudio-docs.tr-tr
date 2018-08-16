---
title: CA2116Ç APTCA yöntemleri yalnızca APTCA yöntemlerini çağırmalıdır
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
helpviewer_keywords:
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
ms.assetid: 8b91637e-891f-4dde-857b-bf8012270ec4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 70affcf0b71e9d0ae7440141f45f5ae0f2c04bf6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31917625"
---
# <a name="ca2116-aptca-methods-should-only-call-aptca-methods"></a>CA2116Ç APTCA yöntemleri yalnızca APTCA yöntemlerini çağırmalıdır
|||
|-|-|
|TypeName|AptcaMethodsShouldOnlyCallAptcaMethods|
|CheckId|CA2116|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir derleme yönteminde <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> özniteliği öznitelik yok. bir bütünleştirilmiş kodunda bir yöntemi çağırır.

## <a name="rule-description"></a>Kural Tanımı
 Varsayılan olarak, güçlü adlara sahip derlemelerde genel ya da korumalı yöntemleri dolaylı olarak tarafından korunan bir [bağlantı talepleri](/dotnet/framework/misc/link-demands) arayanlar tanımlayıcı adlı bir derleme erişmek için tam güven; yalnızca tam olarak güvenilir. Tanımlayıcı adlı derlemeler ile işaretlenen <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) özniteliği bu koruma sahip değil. Öznitelik bütünleştirilmiş kod bir intranet veya Internet yürütme gibi tam güven yok çağıranlar için erişilebilir hale getirme bağlantı isteği devre dışı bırakır.

 APTCA özniteliği üzerinde tam olarak güvenilir bir derleme var ve derlemeyi kısmen güvenilen arayanlara izin verme başka bir derlemede kodu yürütür, güvenlik açığından yararlanma mümkün değildir. İki yöntem `M1` ve `M2` aşağıdaki koşullara uyan, zararlı çağıranlar yöntemi kullanabileceğiniz `M1` korur örtük tam güven bağlantı isteği atlamak için `M2`:

-   `M1` genel yöntem APTCA özniteliği tam güvenilen bir derlemede bildirildi.

-   `M1` bir yöntemi çağırır `M2` dışında `M1`'s derleme.

-   `M2`kişinin derleme APTCA özniteliği yok ve bu nedenle, kısmen güvenilen arayanlara adına ya da tarafından yürütülmesi gereken değil.

 Kısmen güvenilen çağıran `X` yöntemini çağırabilir `M1`, neden `M1` çağırmak için `M2`. Çünkü `M2` anında arayanlar APTCA özniteliği yok (`M1`) bir bağlantı isteği için tam güven; karşılaması gerekir `M1` tam güvene sahip ve bu nedenle bu onay karşılar. Güvenlik riski çünkü `X` korur bağlantı isteği çağıran katılmayan `M2` güvenilmeyen arayanlar gelen. Bu nedenle, APTCA özniteliği yöntemleriyle özniteliğine sahip olmayan yöntemleri çağırmamalıdır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 APCTA özniteliği gerekli ise, bir isteğe bağlı tam güveni derlemesini çağıran yöntemi korumak için kullanın. Tam izinler yöntemi tarafından kullanıma sunulan işlevsellikten, isteğe bağlıdır. Mümkünse, alttaki işlevsellik kısmen güvenilen arayanlara gösterilmeyen emin olmak tam güven için talep yöntemiyle koruyun. Bu mümkün değilse, etkili bir şekilde kullanıma sunulan işlevselliği koruyan bir izin kümesi seçin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural bir uyarıdan güvenle gizlemek için yöntemi tarafından kullanıma sunulan işlevsellikten doğrudan veya dolaylı olarak hassas bilgileri, işlemler veya zararlı bir şekilde kullanılabilir kaynaklara erişmek arayanlara izin vermiyor olduğundan emin olmalısınız.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bu kural tarafından algılanan güvenlik açığı göstermek için iki derleme ve test uygulaması kullanır. İlk derleme APTCA özniteliği yok ve kısmen güvenilen arayanlara erişilebilir olmamalıdır (tarafından temsil edilen `M2` önceki tartışma içinde).

 [!code-csharp[FxCop.Security.NoAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_1.cs)]

## <a name="example"></a>Örnek
 İkinci derleme tam olarak güvenilmeyen ve kısmen güvenilen arayanlara izin verir (tarafından temsil edilen `M1` önceki tartışma içinde).

 [!code-csharp[FxCop.Security.YesAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_2.cs)]

## <a name="example"></a>Örnek
 Test uygulaması (tarafından temsil edilen `X` Önceki tartışmaya) kısmen güvenilir.

 [!code-csharp[FxCop.Security.TestAptcaMethods#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_3.cs)]

 Bu örnek şu çıkışı üretir.

 **İsteğe bağlı olarak tam güven: istek başarısız oldu. ** 
 **ClassRequiringFullTrust.DoWork çağrıldı.**
## <a name="related-rules"></a>İlgili kuralları
 [CA2117: APTCA türleri yalnızca APTCA taban türlerini genişletmelidir](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)

## <a name="see-also"></a>Ayrıca Bkz.
 [Güvenli kodlama yönergeleri](/dotnet/standard/security/secure-coding-guidelines) [kitaplıklarından kısmen kullanarak güvenilen kod](/dotnet/framework/misc/using-libraries-from-partially-trusted-code) [bağlantı talepleri](/dotnet/framework/misc/link-demands) [veri ve modelleme](/dotnet/framework/data/index)