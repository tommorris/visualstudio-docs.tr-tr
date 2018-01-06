---
title: "CA1809: aşırı yerel öğelerden Kaçın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1809
- AvoidExcessiveLocals
helpviewer_keywords:
- AvoidExcessiveLocals
- CA1809
ms.assetid: 5c81ea43-cb49-448f-980f-a1dd9764043c
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8a21f6f7b24151bc1696c409c940cf8e017f9569
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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