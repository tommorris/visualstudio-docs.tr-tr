---
title: 'CA1822: Üyeleri statik olarak işaretle | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- MarkMembersAsStatic
- CA1822
helpviewer_keywords:
- MarkMembersAsStatic
- CA1822
ms.assetid: 743f0af7-41d1-4852-8d97-af0688b31118
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7524db68b984155a8a03f1f0cb1cce0373b382a3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1822-mark-members-as-static"></a>CA1822: Üyeleri statik olarak işaretleyin
|||  
|-|-|  
|TypeName|MarkMembersAsStatic|  
|CheckId|CA1822|  
|Kategori|Microsoft.Performance|  
|Yeni Değişiklik|Bölünemez - üye derleme dışında görünür değilse bağımsız olarak, değişiklik. Örnek üyesine ile üye yalnızca değiştirirseniz olmayan sonu - `this` anahtar sözcüğü.<br /><br /> -Statik bir üyeye bir örnek üyeden üye değiştirirseniz ve derlemenin dışından görülebilir kesiliyor.|  
  
## <a name="cause"></a>Sebep  
 Örnek veri erişmez üyesi static olarak işaretlenmemiş (paylaşılan [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).  
  
## <a name="rule-description"></a>Kural Tanımı  
 Örnek verileri veya çağrı örneği yöntemleri erişmemesi üyeleri işaretlenir olarak statik (paylaşılan [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]). Yöntemleri statik olarak işaretledikten sonra, derleyici sanal olmayan arama sitelerini bu üyelere yayar. Sanal olmayan arama siteleri yayma geçerli nesne işaretçisi null olmayan olmasını sağlayan her çağrı için çalışma zamanında bir onay engeller. Bu performans duyarlı kodu için ölçülebilir performans kazanç elde edebilirsiniz. Bazı durumlarda, geçerli nesne örneği erişimi hatası bir doğruluk sorunu temsil eder.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Üye statik olarak işaretle (veya paylaşılan [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) ya da 'this' kullanmak / yönteminde ' Me' body, uygun olduğunda.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bir düzeltme önemli bir değişiklik olacak önceden sevk edilen kodu için bu kuraldan gizlemek güvenlidir.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1811: Çağrılmayan özel kodlardan kaçının](../code-quality/ca1811-avoid-uncalled-private-code.md)  
  
 [CA1812: Örneklendirilmemiş iç sınıflardan kaçının](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)  
  
 [CA1804: Kullanılmayan yerel öğeleri kaldırın](../code-quality/ca1804-remove-unused-locals.md)