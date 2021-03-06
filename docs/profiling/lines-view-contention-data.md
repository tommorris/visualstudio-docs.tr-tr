---
title: Satırlar görünümü - çakışma verileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Lines view
ms.assetid: 859b02d2-eddf-4ad3-95de-0df67ee2ab03
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ae52ad47e18a0572a883c50f43689bdaae60234d
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34843857"
---
# <a name="lines-view---contention-data"></a>Satırlar görünümü - çakışma verileri
Satırlar görünümü Çekişme veri örnekleri profil Çalıştır toplanan yükleyen yürütülmekte deyimleri için performans verilerini listeler. Bir kaynak dosyasında bir deyim bir kaynak dosyasında birden fazla satırı kapsayabilir ve tek bir satıra birden fazla deyim içerebilir.  
  
 Bir deyim tarafından aşağıdaki veri tanımlanır:  
  
-   Function deyimi içeren kaynak dosyası.  
  
-   Deyimi içeren işlev.  
  
-   Deyim başlatan kaynak satırı.  
  
-   Deyim başlatan kaynak satırdaki karakter.  
  
-   Deyim erdiği kaynak satırı.  
  
-   Deyim erdiği kaynak satırdaki karakter.  
  
 Satır ad sütunu tanımlayıcısı verileri sıralanabilir bir birleşimini sağlar.  
  
 Satırlar görünümü rapor sütunlarını aşağıdaki tabloda açıklanmaktadır.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Özel engellenen süresi**|Bir çakışma olayı nedeniyle deyiminde kod yürütülmesini sırasında bu bildirimi engellendi süre miktarı. Engellenen zamanında deyim adlı işlevleri dahil değildir.|  
|**Özel engellenen süresi %**|Özel engellenen süresi deyiminin işlemdeki tüm engellenen zamanı yüzdesi.|  
|**Özel çekişmeleri**|Bu deyim bir çakışma olayı nedeniyle deyiminde kod yürütülmesini engellendi sayısı. Çekişme olayları deyim adlı işlevlerinde dahil edilmez.|  
|**Özel çekişmeleri %**|Bu deyiminin özel çekişmeleri olan tüm Çekişme olayları işleminde yüzdesi.|  
|**İşlev adresi**|Bu deyim içeren işlevi adresi.|  
|**İşlev adı**|Bu deyim içeren işlevi tam adı.|  
|**Dahil engellenen süre**|Engellenen bu deyimi ve İşlevler deyiminde çağrılır.|  
|**Kapsayıcı engellenen süresi %**|Deyiminin dahil engellenen süresi işlemdeki tüm engellenen zamanı yüzdesi.|  
|**Kapsayıcı çekişmeleri**|Kaç kez bu deyimi ve deyiminde adı veriliyordu işlevleri yürütülmesini engellendi olduğunu.|  
|**Kapsayıcı çekişmeleri %**|Bu deyiminin dahil çekişmeleri olan tüm Çekişme olayları işleminde yüzdesi.|  
|**Satırı adı**|Satırı profil oluşturucu ürettiği tanıtıcısı. Tanımlayıcı aşağıdaki söz dizimini kullanır:`SourceFile`**; [**  `LineNumberStart` **,**`CharacterStart`**] ->; [** `LineNumberEnd`**,**`CharacterEnd`**]**|  
|**İşlev satır numarası**|Bu işlev kaynak dosyadaki başlangıç satır sayısı.|  
|**Modül adı**|Deyim içeren modülü adı.|  
|**Modül yolu**|Deyim içeren modülü yolu.|  
|**İşlem kimliği**|İşlem kimliği (PID) profili işleminin.|  
|**İşlem adı**|İşlemin adı.|  
|**Kaynak karakter başlangıç**|Bu bildirimi başlatan kaynak dosyası satırı başlangıç karakteri uzaklığı.|  
|**Kaynak karakter ucu**|Bu bildirimi erdiği kaynak dosyası satırı başlangıç karakteri uzaklığı.|  
|**Kaynak dosya**|Function deyimi içeren kaynak dosyasının adı.|  
|**Kaynak satırı başlangıç**|Deyim başlatan kaynak dosyasında satır numarası.|  
|**Kaynak satır sonu**|Deyim erdiği kaynak dosyasında satır numarası.|  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Nasıl yapılır: rapor görünümü sütunlarını özelleştirme](../profiling/how-to-customize-report-view-columns.md)   
 [Satırlar görünümü](../profiling/lines-view.md)   
 [Satırlar görünümü - örnekleme](../profiling/lines-view-dotnet-memory-sampling-data.md)   
 [Satırlar Görünümü](../profiling/lines-view-sampling-data.md)