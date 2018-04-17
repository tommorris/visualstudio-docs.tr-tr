---
title: 'CA1809: aşırı yerel öğelerden Kaçın | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1809
- AvoidExcessiveLocals
helpviewer_keywords:
- AvoidExcessiveLocals
- CA1809
ms.assetid: 5c81ea43-cb49-448f-980f-a1dd9764043c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 63bdcf0ea8363e6deb16034011d0a4446594171f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1809-avoid-excessive-locals"></a>CA1809: Aşırı yerel öğelerden kaçın
|||  
|-|-|  
|TypeName|AvoidExcessiveLocals|  
|CheckId|CA1809|  
|Kategori|Microsoft.Performance|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir üye bazıları derleyicinin ürettiği olabilir 64 taneden fazla yerel değişken içeriyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir işlemci kaydı olarak adlandırılır bellekte bir değer depolamak için genel bir performans iyileştirme *enregistering* değeri. Ortak dil çalışma zamanı enregistration için en fazla 64 yerel değişkenleri göz önünde bulundurur. İşlemiyor olmayan değişkenleri yığında yerleştirilir ve işleme önce kasadaki taşınması gerekir. Fırsat izin vermek için tüm yerel değişkenler işlemiyor almak, yerel değişkenleri 64 sayısı sınırı.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için en fazla 64 yerel değişkenleri kullanma uygulaması yeniden düzenleyin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Performans sorunu değilse, bu kural bir uyarıdan gizlemek veya kuralı devre dışı bırakmak için güvenlidir.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1804: Kullanılmayan yerel öğeleri kaldırın](../code-quality/ca1804-remove-unused-locals.md)