---
title: "CA1030: uygun yerlerde olaylar kullanın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UseEventsWhereAppropriate
- CA1030
helpviewer_keywords:
- CA1030
- UseEventsWhereAppropriate
ms.assetid: ea051367-deeb-40f9-9b65-eb818f1e133a
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4c07aac3780abc10dd3995b21b5c9636607166f8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1030-use-events-where-appropriate"></a>CA1030: Uygun yerlerde olaylar kullanın
|||  
|-|-|  
|TypeName|UseEventsWhereAppropriate|  
|CheckId|CA1030|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir ortak, korumalı veya özel yöntem adı aşağıdakilerden biri ile başlar:  
  
-   Eklentisi  
  
-   RemoveOn  
  
-   Yangın  
  
-   Yükselt  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural, normalde olaylar için kullanılan adlara sahip yöntemleri algılar. Olayları gözlemci veya yayımlama-abone olma tasarım deseni izler; Bunlar, bir nesne durum değişikliği diğer nesnelere iletilmelidir olduğunda kullanılır. Yanıt açıkça tanımlanmış durumu değişikliği için bir yöntem olarak adlandırılan, bir olay işleyici tarafından yöntemi çağrılmalıdır. Yöntemi direkt olarak çağırmak yerine olayları yükselterek çağıran nesneler.  
  
 Burada bir düğmeye tıklanması gibi bir kullanıcı eylemi yürütmek için kod kesimi neden olan kullanıcı arabirimi uygulamalarda olayları ortak bazı örnekleri bulunamadı. [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Olay modeli için kullanıcı arabirimleri sınırlı değildir; bu gerekir iletişim durumu değiştirir. bir veya daha fazla nesneye her yerden kullanılmalıdır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bir nesnenin durumunu değiştirdiğinde yöntemi çağrıldıysa kullanmak için tasarım değiştirme düşünmelisiniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] olay modeli.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Yöntemi ile çalışmıyorsa bu kuraldan bir uyarı bastırma [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] olay modeli.