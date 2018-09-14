---
title: 'CA1030: Uygun yerlerde olaylar kullanın'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UseEventsWhereAppropriate
- CA1030
helpviewer_keywords:
- CA1030
- UseEventsWhereAppropriate
ms.assetid: ea051367-deeb-40f9-9b65-eb818f1e133a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6d1b0bac434ad7a182dc56ac08173646068623bd
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45547559"
---
# <a name="ca1030-use-events-where-appropriate"></a>CA1030: Uygun yerlerde olaylar kullanın
|||
|-|-|
|TypeName|UseEventsWhereAppropriate|
|CheckId|CA1030|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Genel, korumalı veya özel yöntem adı aşağıdakilerden biri ile başlar:

- Eklenti fiyatı

- RemoveOn

- Ateş

- artırma

## <a name="rule-description"></a>Kural açıklaması
 Bu kural, normalde olaylar için kullanılan adlara sahip yöntemleri algılar. Olayları gözlemci ya da Yayımla-abone ol tasarım desenini izler; Bunlar, bir nesnede bir durum değişikliği diğer nesnelere iletileceği olduğunda kullanılır. Yanıt olarak açıkça tanımlanmış bir durum değişikliği bir yöntem çağrıldığında, bir olay işleyicisi tarafından yöntemin çağrılması gerekir. Yöntemi direkt olarak çağırmak yerine olayları yükselterek çağıran nesneler.

 Olayların bazı genel örnekleri burada bir düğmeye tıklanması gibi bir kullanıcı eylemi yürütmek için kod kesiminin neden olan kullanıcı arabirimi uygulamalarında bulunur. [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Olay modeli için kullanıcı arabirimleri sınırlı değil; bunu her yerden, iletişim kurması gereken durumu değiştirir. bir veya daha fazla nesneye kullanılmalıdır.

## <a name="how-to-fix-violations"></a>İhlaller nasıl düzeltilir?
 Bir nesnenin durumu değiştiğinde yöntemi çağrılırsa, kullanılacak tasarım değiştirme düşünmelisiniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] olay modeli.

## <a name="when-to-suppress-warnings"></a>Uyarılar bastırıldığında
 Yöntem ile çalışmazsa bu kuraldan bir uyarıyı bastırmak [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] olay modeli.