---
title: "DA0501: İşlemin ortalama CPU kullanımının profili oluşturuluyor. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.rules.DA0501
- vs.performance.DA0501
- vs.performance.501
ms.assetid: b01946b4-75e3-47d5-a1a1-cebfae66a3af
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b17920bea82eff6e71176ff0493faf063d4c2161
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="da0501-average-cpu-consumption-by-the-process-being-profiled"></a>DA0501: İşlemin ortalama CPU kullanımının profili oluşturuluyor.
|||  
|-|-|  
|Kural Kimliği|DA501|  
|Kategori|Kaynak İzleme|  
|Profil oluşturma yöntemi|Tümü|  
|İleti|Ortalama CPU kullanımının profili oluşturuluyor işlem.|  
|Kural türü|Bilgiler|  
  
 Örnekleme, .NET bellek veya kaynak çakışması yöntemlerini kullanarak profil, bu kural tetiklemek için en az 10 örnekleri toplamanız gerekir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu ileti bir işlemci yönergeleri uygulamadan çalıştırmakla meşgul zamanın yüzde olarak bildirir. Bildirilen ortalama profili oluşturuluyor işlem etkin olan tüm ölçüm aralıklarında değerdir. Değerini birden fazla işlemciye sahip bir makinede % 100'den büyük olabilir.  
  
## <a name="how-to-use-rule-data"></a>Kural verileri kullanma  
 Farklı sürümlerini performansını veya programın derlemeleri karşılaştırmak için veya farklı bir test senaryoları altında uygulamanın performansını anlamak için kuralı değeri kullanın.