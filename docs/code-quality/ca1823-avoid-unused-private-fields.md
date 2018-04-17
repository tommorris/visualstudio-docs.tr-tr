---
title: 'CA1823: kullanılmayan özel alanlardan kaçının | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- AvoidUnusedPrivateFields
- CA1823
helpviewer_keywords:
- AvoidUnusedPrivateFields
- CA1823
ms.assetid: 614f94f6-0dc7-430f-8124-cb889a4a720f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fa8af282866cd871d2717031091215cb431e1ec0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1823-avoid-unused-private-fields"></a>CA1823: Kullanılmayan özel alanlardan kaçının
|||  
|-|-|  
|TypeName|AvoidUnusedPrivateFields|  
|CheckId|CA1823|  
|Kategori|Microsoft.Performance|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bu kural, kodunuzda özel bir alan var, ancak hiçbir kod yolu tarafından kullanılmayan zaman bildirilir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Derlemede erişimi görülmeyen özel alanlar algılandı.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için alanı kaldırın veya bu kullanan kodu ekleyin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan gizlemek güvenlidir.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1812: Örneklendirilmemiş iç sınıflardan kaçının](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)  
  
 [CA1801: Kullanılmayan parametreleri gözden geçir](../code-quality/ca1801-review-unused-parameters.md)  
  
 [CA1804: Kullanılmayan yerel öğeleri kaldırın](../code-quality/ca1804-remove-unused-locals.md)  
  
 [CA1811: Çağrılmayan özel kodlardan kaçının](../code-quality/ca1811-avoid-uncalled-private-code.md)