---
title: Görünüm - çakışma verileri işlemek | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Process view
ms.assetid: 8821d98c-0771-43b2-a38b-e9039a3abd75
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 41212ffb6b317d7c98a50b074d93c128977a5a82
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="process-view---contention-data"></a>İşlem görünümü - çakışma verileri
İşlem görünümü işlemleri ve profil oluşturma çalışması sırasında yürütüldü iş parçacıklarını Çekişme verilerini görüntüler.  
  
 Simgeler kullanılabildiğinde, işlemleri adına göre listelenmiştir. Semboller kullanılabilir olmadığında, işlemleri kendi bellek adresi onaltılık biçimde göre listelenir. İş parçacığı onları oluşturan işlemin alt öğesi olarak listelenir.  
  
 İşlem görünümü tablodaki sütun değerleri aşağıdaki tabloda açıklanmaktadır.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Başlangıç zamanı**|Milisaniye veya işlemci döngülerinin sayısı işlemin veya iş parçacığı başına profil oluşturma başından.|  
|**Engellenen zaman**|Toplam süre yürütülmesini sırasında hangi işlemin veya iş parçacığı işlevlerini engellendi.|  
|**Engellenen süresi %**|İşlem veya iş parçacığı işlevlerini yürütülmesini engellendi iş parçacığı ve işlem ömrü yüzdesi.|  
|**Çekişmeleri**|İş parçacığı ve işlem işlevlerini yürütülmesini engellendi sayısı.|  
|**Çekişmeleri %**|Profil çalıştıran tüm çekişmeleri yüzdesi işlem veya iş parçacığı çekişmeleri yoktu.|  
|**Bitiş saati**|Milisaniye veya işlemci döngülerinin sayısı işlemin veya iş parçacığı sonuna profil oluşturma başından.|  
|**ID**|Sistem tarafından oluşturulan tanımlayıcısını iş parçacığı ve işlem.|  
|**Yaşam süresi**|Milisaniye veya işlemci döngülerinin sayısı işlemin veya iş parçacığı iş parçacığı ve işlem sonuna veya profil sonu başlangıcı.|  
|**Türü**|Satırın, türü işlem veya iş parçacığı.<br /><br /> Yalnızca **VSReport** komut satırı raporlar. Daha fazla bilgi için bkz: [VSPerfReport](../profiling/vsperfreport.md).|  
|**Ad**|İş parçacığı ve işlem adı.|  
|**Benzersiz kimliği**|İş parçacığı ve işlem için benzersiz bir profil oluşturucu tarafından oluşturulan bir tanımlayıcı.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: rapor görünümü sütunlarını özelleştirme](../profiling/how-to-customize-report-view-columns.md)   
 [İşlem Görünümü](../profiling/process-view.md)