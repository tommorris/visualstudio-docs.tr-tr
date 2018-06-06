---
title: 'DA0001: Birleştirmeler için StringBuilder kullanın | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0001
- vs.performance.rules.DAUseStringBuilder
- vs.performance.1
- vs.performance.rules.DA0001
ms.assetid: a7cc7613-ad5f-48c8-bd2b-56372cc12dfc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2b073640670d3e6e650fc4144c61e971c085aec2
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749730"
---
# <a name="da0001-use-stringbuilder-for-concatenations"></a>DA0001: Birleştirmeler için StringBuilder kullanın
|||  
|-|-|  
|Kural Kimliği|DA0001|  
|Kategori|.NET framework kullanımı|  
|Profil oluşturma yöntemleri|Örnekleme<br /><br /> İzleme|  
|İleti|Dize birleştirmeler için StringBuilder kullanmayı düşünün|  
|İleti türü|Uyarı|  
  
## <a name="cause"></a>Sebep  
 Profil oluşturma verileri önemli bir kısmının System.String.Concat çağrıları aynıdır. Kullanmayı <xref:System.Text.StringBuilder> birden çok parçalı dizelerden oluşturmak için sınıfı.  
  
## <a name="rule-description"></a>Kural açıklaması  
 A <xref:System.String> nesnesidir değişmez. Bu nedenle, dize kendilerine herhangi bir değişiklik yeni bir dize nesnesi ve özgün çöp koleksiyonu oluşturur. Dize birleştirme işleçleri kullanın veya String.Concat açıkça çağırın Bu davranış aynı olup + veya +=... Varsa program performans düşebilir zaman karakter sıkı bir döngü içindeki bir dizeye eklenen gibi bu yöntemleri sık denir.  
  
 StringBuilder sınıfını değişebilir bir nesnedir ve System.String, bu sınıfın bir örneğini değiştirmek StringBuilder yöntemlerde çoğunu o aynı örneğine başvuru dönün. Karakterleri eklemek veya bir StringBuilder örneğine metin ekleyin ve kaldırın veya yeni bir örneğini ayırma ve orijinal örnek silmek için gerek kalmadan örnekteki karakterleri değiştirin.  
  
## <a name="how-to-investigate-a-warning"></a>Bir uyarıyı araştırmak nasıl  
 İletide çift **hata listesi** gitmek için pencere [işlev Ayrıntıları görünümü](../profiling/function-details-view.md) örnekleme, profil verileri. Dize birleştirme en sık rastlanan kullanılmasını sağlamak program bölümlerini bulur. StringBuilder sınıfını sık dize birleştirme işlemleri dahil olmak üzere karmaşık dize işlemeleri için kullanın.  
  
 Dizeleri ile birlikte çalışma hakkında daha fazla bilgi için [dize işlemleri](http://go.microsoft.com/fwlink/?LinkId=177816) bölümünü [bölüm 5 - yönetilen kod performansı artırma](http://go.microsoft.com/fwlink/?LinkId=177817) Microsoft Patterns and Practices Kitaplığı'nda.