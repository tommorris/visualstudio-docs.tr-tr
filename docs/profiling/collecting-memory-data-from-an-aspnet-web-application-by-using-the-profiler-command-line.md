---
title: "Profil oluşturucu komut satırını kullanarak bir ASP.NET Web uygulamasından bellek verileri toplama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET memory profiling method
- profiling tools,.NET memory method
ms.assetid: 57acf2b0-327a-4c0e-8078-ac2f6d99457d
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: aspnet
ms.openlocfilehash: f839156c470f14097e216f55318cf94f123f5c91
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="collecting-memory-data-from-an-aspnet-web-application-by-using-the-profiler-command-line"></a>Profil Oluşturucu Komut Satırını Kullanarak bir ASP.NET Web Uygulamasından Bellek Verileri Toplama
Bu bölümdeki yordamları ve kullanarak bir ASP.NET Web uygulaması için bellek ayırma ve nesne yaşam verisi toplama için seçenekleri açıklar **VSPerfCmd** komut satırı aracı.  
  
> [!NOTE]
>  **VSPerfCmd** aracı duraklatma ve sürdürme profil oluşturma ve ek veri işlemci ve Windows performans sayaçlarını toplama dahil olmak üzere profil oluşturma araçları işlevine tam erişimi olan, sağlar. Aynı zamanda **VSPerfASPNETCmd** bu işlevselliği gerekmediğinde komut satırı aracı. İle karşılaştırılan [VSPerfCmd](../profiling/vsperfcmd.md) komut satırı aracı, ortam değişkenleri ayarlanmış olması gerekir ve bilgisayar yeniden başlatıldığı gerekli değildir. Daha fazla bilgi için bkz: [VSPerfASPNETCmd ile Hızlı Web sitesi profil](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md).  
  
## <a name="common-tasks"></a>Ortak Görevler  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Çalışan bir ASP.NET uygulamasına profil oluşturucu ekleme**|-   [Nasıl yapılır: bellek verileri toplamak için bir ASP.NET Web uygulamasına profil oluşturucu ekleme](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-memory-data-by-using-the-command-line.md)|  
|**Statik olarak derlenmiş gereç ikili dosyalar**|-   [Nasıl yapılır: statik olarak derlenmiş bir ASP.NET uygulamasını izleme ve bellek verileri toplama](../profiling/how-to-instrument-a-statically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line.md)|  
|**Dinamik olarak derlenmiş gereç ikili dosyalar**|-   [Nasıl yapılır: dinamik olarak derlenmiş bir ASP.NET uygulamasını izleme ve bellek verileri toplama](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line.md)|  
  
## <a name="related-tasks"></a>İlgili görevleri  
  
### <a name="profiling-aspnet-web-applications"></a>ASP.NET Web Uygulamalarında Profil Oluşturma  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Örnekleme yöntemini kullanarak profil**|-   [Örnekleme kullanarak uygulama istatistikleri toplama](../profiling/collecting-application-statistics-for-aspnet-web-applications-using-the-profiler-sampling-method-from-the-command-line.md)|  
|**İzleme metodunu kullanarak profil**|-   [İzleme kullanarak ayrıntılı zamanlama verileri toplama](../profiling/collecting-detailed-timing-data-for-an-aspnet-web-application-using-the-profiler-instrumentation-method-from-the-command-line.md)|  
|**Kaynak çakışması ve iş parçacığı etkinliği profil**|-   [Eşzamanlılık verileri toplama](../profiling/collecting-concurrency-data-for-an-aspnet-web-application-using-the-profiler-command-line.md)|  
  
### <a name="profiling-net-framework-memory-data"></a>.NET Framework bellek verileri profil oluşturma  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Profil tek başına (istemci) uygulamaları**|-   [.NET Framework bellek verileri toplama](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Profil Hizmetleri**|-   [.NET bellek verileri toplama](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
  
### <a name="analyzing-net-memory-data-views-and-reports"></a>.NET bellek verileri analiz etme, görünümler ve raporlar  
 [.NET bellek verisi görünümleri](../profiling/dotnet-memory-data-views.md)  
  
## <a name="reference"></a>Başvuru  
 [Komut satırı profil araçları başvurusu](../profiling/command-line-profiling-tools-reference.md)