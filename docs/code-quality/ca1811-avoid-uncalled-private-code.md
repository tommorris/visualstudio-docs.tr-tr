---
title: 'CA1811: çağrılmayan özel kodlardan kaçının | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
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
ms.openlocfilehash: 8d9015fe8b7384046b621cd11600528cd76a97c1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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