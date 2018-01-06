---
title: "DA0506: Maksimum özel bayt sayısının profili oluşturuluyor işlemi için ayrılan | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.rules.DA0506
- vs.performance.DA0506
- vs.performance.506
ms.assetid: e9c43554-9a85-4d98-9fa4-3b19986e7b62
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4a624e790a618f923f5a70981fc3fef32809966d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="da0506-maximum-private-bytes-allocated-for-the-process-being-profiled"></a>DA0506: İşlem için izin verilen Maksimum Özel Bayt Sayısının profili oluşturuluyor
|||  
|-|-|  
|Kural Kimliği|DA0506|  
|Kategori|Kaynak İzleme|  
|Profil oluşturma yöntemi|Tümü|  
|İleti|Bu bilgiler yalnızca bilgi toplandı. İşlem özel bayt sayısı sayacı, profil işlem tarafından ayrılan sanal bellek ölçer. Değer, en fazla tüm ölçüm aralıklarında gözlenir bildirdi.|  
|Kural türü|Bilgiler|  
  
 Örnekleme, .NET bellek veya kaynak çakışması yöntemlerini kullanarak profil, bu kural tetiklemek için en az 10 örnekleri toplamanız gerekir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu ileti en fazla işlem bayt (özel bayt) şu anda ayrılmış sanal bellek miktarı bildirir. Özel bayt yalnızca işlem içinde çalışan iş parçacıkları tarafından erişilebilecek bir işlem tarafından ayrılan sanal bellek konumlarını temsil eder.  
  
 Bir 32-bit makine üzerinde çalışan 32 bit işlemler için işlem adres alanı özel bölümünü sayısı üst sınırı 2 GB'dir. Kullanarak [3 GB](http://go.microsoft.com/fwlink/?LinkId=177831) Boot.ini anahtarı, 32 bit işlemler 3 GB sanal bellek elde. Bir 64-bit makine üzerinde çalışan 32 bitlik bir işlem en fazla 4 GB özel sanal bellek elde edebilirsiniz.  
  
 Bir 64-bit makine üzerinde çalışan 64 bitlik bir işlem özel sanal bellek 8 TB'ye kadar elde edebilirsiniz.  
  
 Bildirilen değeri en fazla profili oluşturuluyor işlem etkin olan tüm ölçüm aralıklarında olabilir.  
  
 İşlem adres alanları hakkında daha fazla bilgi için bkz: [sanal adres alanı](http://go.microsoft.com/fwlink/?LinkId=177832) Windows bellek yönetimi belgelerinde.  
  
## <a name="how-to-use-rule-data"></a>Kural verileri kullanma  
 Bildirilen değeri farklı sürümlerini performansını veya programın derlemeleri karşılaştırmak ya da farklı profil oluşturma senaryoları altında uygulamanın performansını anlamak için kullanın.  
  
 Ne kadar büyük bir işlem adres alanı büyüyebileceğinin mimari sınırına yaklaşıyor bir maksimum değer işlem özel bayt belleği özel durumları out neden olabilir. Daha fazla bilgi için bkz: [bellek sorunları araştırma](http://go.microsoft.com/fwlink/?LinkID=177833) MSDN dergisi içinde.