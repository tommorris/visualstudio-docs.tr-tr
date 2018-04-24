---
title: Profil oluşturma raporları komut satırından Basic oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 6d73e21e-c04e-48ea-91cc-e517a5f2cd3f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 502fe56f04fe933e51e9afa5376a35a53445c099
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="creating-basic-profiling-reports-from-the-command-line"></a>Komut Satırından Temel Profil Oluşturma Raporları Oluşturma
Bu konuda .vsp ya da veri dosyası profil .vsps virgülle ayrılmış değer (.csv) raporlar üretmek temel VSPerfReport komutları açıklanmaktadır. Tüm rapor seçeneklerini açıklaması için bkz: [VSPerfReport](../profiling/vsperfreport.md).  
  
## <a name="report-commands"></a>Rapor komutları  
 Belirtilen bir profil oluşturma veri dosyası için bir rapor oluşturmak için aşağıdaki komutlardan birini kullanın.  
  
 **VSPerfReport** `VSPFile` **/Summary:All**  
 .Vsp ya da .vsps dosyası için kullanılabilir tüm raporlar oluşturur.  
  
 **VSPerfReport** `VSPFile` **/Özet:**`ReportType`[,`ReportType`...]  
 Belirtilen rapor türleri oluşturur.  
  
 **VSPerfReport** `VSPFile` **/CallTrace**  
 Her veri koleksiyonu olayı listeleyen bir rapor oluşturur. Yalnızca araçları.  
  
## <a name="summary-report-type-parameters"></a>Özet raporu tür parametreleri  
 Aşağıdaki tabloda belirtilen rapor türü seçeneği tarafından oluşturulan raporları açıklar. Bir rapor sütunlarını verileri toplamak için kullanılan profil yöntemine bağlıdır.  
  
|Özet parametresi|Rapor açıklaması|Rapor başvurusu|  
|-----------------------|------------------------|----------------------|  
|**CallerCallee**|Üst/alt ilişkilerini işlevlerini temsil eder.|-   [Örnekleme verileri](../profiling/caller-callee-view-sampling-data.md)<br />-   [İzleme verileri](../profiling/caller-callee-view-instrumentation-data.md)<br />-   [.NET bellek örnekleme verileri](../profiling/caller-callee-view-dotnet-memory-sampling-data.md)<br />-   [.NET bellek izleme verileri](../profiling/caller-callee-view-net-memory-instrumentation-data.md)<br />-   [Çakışma verileri](../profiling/caller-callee-view-contention-data.md)|  
|**İşlevi**|İşlev tarafından profil oluşturma verilerini listeler.|-   [Örnekleme verileri](../profiling/functions-view-sampling-data.md)<br />-   [İzleme verileri](../profiling/functions-view-instrumentation-data.md)<br />-   [.NET bellek örnekleme verileri](../profiling/functions-view-dotnet-memory-sampling-data.md)<br />-   [.NET bellek izleme verileri](../profiling/functions-view-dotnet-memory-instrumentation-data.md)<br />-   [Çakışma verileri](../profiling/functions-view-contention-data.md)|  
|**CallTree**|Yürütme yolları ve profil oluşturma Çalıştır işlevlerin profil oluşturma verileri temsil eder.|-   [İzleme verileri](../profiling/call-tree-view-instrumentation-data.md)<br />-   [Örnekleme verileri](../profiling/call-tree-view-sampling-data.md)<br />-   [.NET bellek örnekleme verileri](../profiling/call-tree-view-dotnet-memory-sampling-data.md)<br />-   [.NET bellek izleme verileri](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)<br />-   [Çakışma verileri](../profiling/call-tree-view-contention-data.md)|  
|**Counter**|Çizgileri ve Çalıştır profili oluşturma sırasında toplanan Windows performans sayacı değerlerini profil listeler.|-   [İşaretler görünümü](../profiling/marks-view.md)|  
|**IP**|Yönerge tarafından profil oluşturma verilerini listeler.|-   [Örnekleme verileri](../profiling/instruction-pointers-ips-view-sampling-data.md)<br />-   [.NET bellek örnekleme verileri](../profiling/instruction-pointers-ips-view-dotnet-memory-sampling-data.md)<br />-   [Çakışma verileri](../profiling/instruction-pointers-ips-view-contention-data.md)|  
|**Ömrü**|Ayrılmış nesnelerin ömrü listeler.|-   [Nesne ömrü görünümü](../profiling/object-lifetime-view.md)|  
|**Satır**|Kaynak kodu satır tarafından profil oluşturma verilerini listeler.|-   [Örnekleme verileri](../profiling/lines-view-sampling-data.md)<br />-   [.NET bellek örnekleme verileri](../profiling/lines-view-dotnet-memory-sampling-data.md)<br />-   [Çakışma verileri](../profiling/lines-view-contention-data.md)|  
|**Üstbilgi**|Profil oluşturma veri dosyası üst bilgileri.|Dosya özgüdür.|  
|**Mark**|İşaretleri Profil Profil Çalıştır toplanır.|-   [İşaretler görünümü](../profiling/marks-view.md)|  
|**Modülü**|Profil oluşturma verilerini modülleri için listeler.|-   [Örnekleme verileri](../profiling/modules-view-sampling-data.md)<br />-   [İzleme verileri](../profiling/modules-view-instrumentation-data.md)<br />-   [.NET bellek örnekleme verileri](../profiling/modules-view-dotnet-memory-sampling-data.md)<br />-   [.NET bellek izleme verileri](../profiling/modules-view-dotnet-memory-instrumentation-data.md)<br />-   [Çakışma verileri](../profiling/modules-view-contention-data.md)|  
|**İşlem**|Profil oluşturma verilerini işlemleri listeler.|-   [İşlem görünümü](../profiling/process-view.md)<br />-   [Çakışma verileri](../profiling/process-view-contention-data.md)|  
|**İş parçacığı**|Profil oluşturma iş parçacıkları için verilerini listeler.|-   [İşlem görünümü](../profiling/process-view.md)|  
|**Türü**|Profil oluşturma verilerini türe göre ayırma listeler.|-   [Ayırmalar görünümü](../profiling/dotnet-memory-allocations-view.md)|  
|**Çekişme**|Kaynak çekişmeleri.|-   [Kaynak çekişmeleri](../profiling/resource-contentions-view-contention-data.md)|  
|**RuleWarnings**|Performans kuralı sorunlarını listeler.|-Checkıd, açıklama ve kaynak kodu kural sorunu konumunu listeler.|  
|**ETW**|Olay izleme için Windows (ETW) olayları çalıştırmak profil toplanmadı.|-   [ETW raporu](../profiling/event-tracing-for-windows-etw-report.md)|