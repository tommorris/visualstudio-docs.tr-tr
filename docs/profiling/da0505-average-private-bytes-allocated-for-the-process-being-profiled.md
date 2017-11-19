---
title: "DA0505: Ortalama özel bayt sayısının profili oluşturuluyor işlemi için ayrılan | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.DA0505
- vs.performance.rules.DA0505
- vs.performance.505
ms.assetid: 32c612ea-d077-44ba-8e6f-3a96333bad00
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c0b3bd538de0d38e4104a2769cb3e6ce079a7cd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="da0505-average-private-bytes-allocated-for-the-process-being-profiled"></a>DA0505: İşlem için izin verilen Ortalama Özel Bayt Sayısının profili oluşturuluyor
|||  
|-|-|  
|Kural Kimliği|DA0505|  
|Kategori|Kaynak Yönetimi|  
|Profil oluşturma yöntemi|Tümü|  
|İleti|Bu bilgiler yalnızca bilgi toplandı. İşlem özel bayt sayısı sayacı, profil işlem tarafından ayrılan sanal bellek ölçer. Tüm ölçüm aralıklarında ortalama hesaplanan değer bildirdi.|  
|Kural türü|Bilgiler|  
  
 Örnekleme, .NET bellek veya kaynak çakışması yöntemlerini kullanarak profil, bu kural tetiklemek için en az 10 örnekleri toplamanız gerekir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu ileti ortalama işlem bayt (özel bayt) şu anda ayrılmış sanal bellek miktarı bildirir. Özel bayt yalnızca işlem içinde çalışan iş parçacıkları tarafından erişilebilecek bir işlem tarafından ayrılan sanal bellek konumlarını temsil eder.  
  
 Bir 32-bit makine üzerinde çalışan 32 bit işlemler için işlem adres alanı özel bölümünü sayısı üst sınırı 2 GB'dir. Kullanarak [3 GB](http://go.microsoft.com/fwlink/?LinkId=177831) Boot.ini anahtarı, 32 bit işlemler 3 GB sanal bellek elde. Bir 64-bit makine üzerinde çalışan 32 bitlik bir işlem en fazla 4 GB özel sanal bellek elde edebilirsiniz.  
  
 Bir 64-bit makine üzerinde çalışan 64 bitlik bir işlem özel sanal bellek 8 TB'ye kadar elde edebilirsiniz.  
  
 Bildirilen değeri profili oluşturuluyor işlem etkin olan tüm ölçüm aralıklarında ortalama değer.  
  
 İşlem adres alanları hakkında daha fazla bilgi için bkz: [sanal adres alanı](http://go.microsoft.com/fwlink/?LinkId=177832) Windows bellek yönetimi belgelerinde.  
  
## <a name="how-to-use-rule-data"></a>Kural verileri kullanma  
 Bildirilen değeri farklı sürümlerini performansını veya programın derlemeleri karşılaştırmak ya da farklı profil oluşturma senaryoları altında uygulamanın performansını anlamak için kullanın.