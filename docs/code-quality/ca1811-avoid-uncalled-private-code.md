---
title: 'CA1811: Çağrılmayan özel kodlardan kaçının'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidUncalledPrivateCode
- CA1811
helpviewer_keywords:
- CA1811
- AvoidUncalledPrivateCode
ms.assetid: aadbba74-7821-475f-8980-34d17c0a0a8b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d7f31b27740b286065221838e733d99e94b3307d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1811-avoid-uncalled-private-code"></a>CA1811: Çağrılmayan özel kodlardan kaçının
|||
|-|-|
|TypeName|AvoidUncalledPrivateCode|
|CheckId|CA1811|
|Kategori|Microsoft.Performance|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Özel veya dahili (derleme düzeyi) üyesi arayanlar derlemede yok, ortak dil çalışma zamanı tarafından çağrılır ve temsilci tarafından çağrılır. Aşağıdaki üyeleri bu kural tarafından denetlenmez:

-   Açık arabirim üyeleri.

-   Statik oluşturucular.

-   Serileştirme oluşturucularını uygulayın.

-   Yöntemleri ile işaretlenen <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> veya <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName>.

-   Geçersiz kılmaları olan üyeleri.

## <a name="rule-description"></a>Kural Tanımı
 Bu kural, giriş noktaları meydana gelirse hatalı pozitif sonuç kural mantığı tarafından şu anda tanımlanmamış bildirebilirsiniz. Ayrıca, bir derleyici noncallable kodu derlemeye yayabilir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için noncallable kodunu kaldırmak veya onu çağıran kodu ekleyin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural bir uyarıdan gizlemek güvenlidir.

## <a name="related-rules"></a>İlgili kuralları
 [CA1812: Örneklendirilmemiş iç sınıflardan kaçının](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1801: Kullanılmayan parametreleri gözden geçir](../code-quality/ca1801-review-unused-parameters.md)

 [CA1804: Kullanılmayan yerel öğeleri kaldırın](../code-quality/ca1804-remove-unused-locals.md)