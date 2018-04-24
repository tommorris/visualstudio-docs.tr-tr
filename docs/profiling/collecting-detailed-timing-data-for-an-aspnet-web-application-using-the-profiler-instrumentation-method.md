---
title: Toplama ayrıntılı zamanlama verileri komut satırından profil oluşturucu izleme yöntemini kullanarak bir ASP.NET Web uygulaması için | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools,instrumentation method
- instrumentation profiling method
ms.assetid: 29f2fc55-aaf7-4e18-a672-8815455fba73
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 3665046320b644ebd9689e14c18cc68b79c95347
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="collecting-detailed-timing-data-for-an-aspnet-web-application-using-the-profiler-instrumentation-method-from-the-command-line"></a>Komut Satırından Profil Oluşturucu İzleme Metodunu Kullanarak bir ASP.NET Web Uygulaması için Ayrıntılı Zamanlama Verileri Toplama
Bu bölümdeki yordamları ve ayrıntılı performans toplamak için seçenekleri açıklar için verileri bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması kullanarak **VSPerfCmd** komut satırı aracı ve izleme yöntemi.  
  
> [!NOTE]
>  **VSPerfCmd** aracı duraklatma ve sürdürme profil oluşturma ve ek veri işlemci ve Windows performans sayaçlarını toplama dahil olmak üzere profil oluşturma araçları işlevine tam erişimi olan, sağlar. Aynı zamanda **VSPerfASPNETCmd** bu işlevselliği gerekmediğinde komut satırı aracı. Comparison için [VSPerfCmd](../profiling/vsperfcmd.md) komut satırı aracı, ortam değişkenleri ayarlanması zorunda ve bilgisayar yeniden başlatıldığı gerekli değildir. Daha fazla bilgi için bkz: [VSPerfASPNETCmd ile Hızlı Web sitesi profil](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md).  
  
## <a name="common-tasks"></a>Ortak Görevler  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Statik olarak derlenmiş ikili dosyaları profil**|-   [Nasıl yapılır: statik olarak derlenmiş bir ASP.NET uygulamasını izleme ve ayrıntılı zamanlama verileri toplama](../profiling/how-to-instrument-a-statically-compiled-aspnet-web-application-and-collect-detailed-timing-data-with-the-profiler-by-using-the-command-line.md)|  
|**Dinamik olarak derlenmiş ikili dosyaları profil**|-   [Nasıl yapılır: dinamik olarak derlenmiş bir ASP.NET uygulamasını izleme ve ayrıntılı zamanlama verileri toplama](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-detailed-timing-data-with-the-profiler.md)|  
  
## <a name="related-tasks"></a>İlgili görevleri  
  
### <a name="profiling-aspnet-web-applications"></a>ASP.NET Web Uygulamalarında Profil Oluşturma  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Örnekleme yöntemini kullanarak profil**|-   [Örnekleme kullanarak uygulama istatistikleri toplama](../profiling/collecting-application-statistics-for-aspnet-web-applications-using-the-profiler-sampling-method-from-the-command-line.md)|  
|**Bellek ayırma ve atık toplama profil**|-   [Bellek verileri toplama](../profiling/collecting-memory-data-from-an-aspnet-web-application-by-using-the-profiler-command-line.md)|  
|**Kaynak çakışması ve iş parçacığı etkinliği profil**|-   [Eşzamanlılık verileri toplama](../profiling/collecting-concurrency-data-for-an-aspnet-web-application-using-the-profiler-command-line.md)|  
  
### <a name="profiling-by-using-the-instrumentation-method"></a>İzleme metodunu kullanarak profil oluşturma  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Profil tek başına (istemci) uygulamaları**|-   [İzleme kullanarak ayrıntılı zamanlama verileri toplama](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application-by-using-the-profiler-command-line.md)|  
|**Profil Hizmetleri**|-   [İzleme kullanarak ayrıntılı zamanlama verileri toplama](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method-from-the-profiler-command-line.md)|  
  
### <a name="analyzing-instrumentation-data-views-and-reports"></a>Görünümler ve raporlar izleme verileri analiz etme  
 [İzleme Metodu Veri Görünümleri](../profiling/instrumentation-method-data-views.md)