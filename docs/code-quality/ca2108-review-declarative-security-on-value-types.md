---
title: 'CA2108: Değer türleri üzerinde bildirimsel güvenliği gözden geçirin'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ReviewDeclarativeSecurityOnValueTypes
- CA2108
helpviewer_keywords:
- ReviewDeclarativeSecurityOnValueTypes
- CA2108
ms.assetid: d62bffdd-3826-4d52-a708-1c646c5d48c2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1d07245724d70b5bc6ba69deae4311dcb2a10056
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2108-review-declarative-security-on-value-types"></a>CA2108: Değer türleri üzerinde bildirimsel güvenliği gözden geçirin
|||
|-|-|
|TypeName|ReviewDeclarativeSecurityOnValueTypes|
|CheckId|CA2108|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Olmayan sonu|

## <a name="cause"></a>Sebep
 Bir genel veya korumalı değer türü tarafından güvenliği sağlanan bir [veri ve modelleme](/dotnet/framework/data/index) veya [bağlantı talepleri](/dotnet/framework/misc/link-demands).

## <a name="rule-description"></a>Kural Tanımı
 Değer türleri ayrılmış ve diğer oluşturucular yürütmeden önce kendi varsayılan oluşturucular tarafından başlatıldı. Değer türü bir isteğe bağlı veya LinkDemand tarafından korunmaktadır ve arayan güvenlik denetimi, tüm Oluşturucusu dışında uygun izinlere sahip değil, varsayılan başarısız olur ve bir güvenlik özel durum. Değer türü serbest değil; kendi varsayılan oluşturucu tarafından ayarlanmış durumda kalır. Değer türü örneği aktardığı çağıran oluşturun veya örneğine erişmek için izne sahip olduğunu varsayın değil.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal güvenlik denetimi türünden kaldırın ve onun yerine kullanım yöntemi düzeyi güvenlik denetimlerini sürece düzeltilemiyor. Bu şekilde ihlali düzelttikten değer türü örnekleri alma gelen yetersiz izinlerle arayanlar önlemez unutmayın. Değer türünde varsayılan durumuna örnek hassas bilgileri kullanıma sunmuyor ve zararlı bir biçimde kullanılamaz emin olmalısınız.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Güvenlik için bir tehdit taşıyor olmadan varsayılan durumuna içinde değer türüne örneklerini herhangi bir çağırıcı elde edebilirsiniz, bu kural bir uyarıdan gizleyebilirsiniz.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bu kural ihlal eden bir değer türü içeren bir kitaplık gösterir. Unutmayın `StructureManager` türü varsayar değer türünün bir örneği aktardığı çağıran oluşturmak veya örneğine erişmek için izne sahip.

 [!code-csharp[FxCop.Security.DemandOnValueType#1](../code-quality/codesnippet/CSharp/ca2108-review-declarative-security-on-value-types_1.cs)]

## <a name="example"></a>Örnek
 Aşağıdaki uygulama kitaplığın zayıflık gösterir.

 [!code-csharp[FxCop.Security.TestDemandOnValueType#1](../code-quality/codesnippet/CSharp/ca2108-review-declarative-security-on-value-types_2.cs)]

 Bu örnek şu çıkışı üretir.

 **Yapı özel Oluşturucusu: isteği başarısız oldu. ** 
 **Yeni değerleri SecuredTypeStructure 100 100**
**yeni değerleri SecuredTypeStructure 200 200**
## <a name="see-also"></a>Ayrıca Bkz.
 [Bağlantı talepleri](/dotnet/framework/misc/link-demands) [veri ve modelleme](/dotnet/framework/data/index)