---
title: Toplama istatistikleri ASP.NET web uygulamaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, sampling method
- sampling profling method
ms.assetid: f8383ab1-eb49-4d3f-8608-d8b4d51a81be
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: ea70f8f665196aff94c04796204881a0e16b261c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="collect-statistics-for-aspnet-web-apps"></a>ASP.NET web uygulamaları için istatistikleri toplama

Bu bölümdeki yordamları ve kullanarak bir ASP.NET Web uygulaması için performans istatistikleri toplamak için seçenekleri açıklar **VSPerfASPNETCmd** ve **VSPerfCmd** komut satırı aracı ve örnekleme profili oluşturma yöntemi.  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
> [!NOTE]
>  Ancak **VSPerfCmd** aracı size tam erişim duraklatma ve profil oluşturma, yeniden başlatma da dahil olmak üzere profil oluşturma araçları işlevselliği için ve ek verileri işlemci ve Windows performans sayaçlarını toplama, kullanmanız gerekir **VSPerfASPNETCmd** bu işlevselliği gerekmediğinde komut satırı aracı. **VSPerfASPNETCmd** komut satırı aracıdır tercih edilen yöntem zaman olduğunuz bağımsız profil oluşturucuyu kullanarak ASP.NET Web siteleri profil oluşturma. İle karşılaştırılan [VSPerfCmd](../profiling/vsperfcmd.md) komut satırı aracı, ortam değişkenleri ayarlanmış olması gerekir ve bilgisayar yeniden başlatıldığı gerekli değildir. Daha fazla bilgi için bkz: [VSPerfASPNETCmd ile Hızlı Web sitesi profil](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md).  
  
## <a name="common-tasks"></a>Ortak Görevler  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Bir ASP.NET uygulamasına profil oluşturucu ekleme**|-   [Nasıl yapılır: uygulama istatistikleri toplamak için bir ASP.NET Web uygulamasına profil oluşturucu ekleme](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-application-statistics-by-using-the-command-line.md)|  
  
## <a name="related-tasks"></a>İlgili görevleri  
  
### <a name="profiling-aspnet-web-applications"></a>ASP.NET Web Uygulamalarında Profil Oluşturma  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**İzleme metodunu kullanarak profil**|-   [İzleme kullanarak ayrıntılı zamanlama verileri toplama](../profiling/collecting-detailed-timing-data-for-an-aspnet-web-application-using-the-profiler-instrumentation-method.md)|  
|**Bellek ayırma ve atık toplama profil**|-   [Bellek verileri toplama](../profiling/collecting-memory-data-from-an-aspnet-web-application-by-using-the-profiler-command-line.md)|  
|**Kaynak çakışması ve iş parçacığı etkinliği profil**|-   [Eşzamanlılık verileri toplama](../profiling/collecting-concurrency-data-for-an-aspnet-web-application-using-the-profiler-command-line.md)|  
  
### <a name="sampling-method"></a>Örnekleme yöntemi  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Profil tek başına (istemci) uygulamaları**|-   [Örnekleme kullanarak uygulama istatistikleri toplama](../profiling/collecting-application-statistics-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|-   **Profil Hizmetleri**|-   [Örnekleme kullanarak uygulama istatistikleri toplama](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md)|  
  
### <a name="analyzing-sampling-data-views-and-reports"></a>Görünümler ve raporlar örnekleme verileri analiz etme  
 [Örnekleme yöntemi veri görünümleri](../profiling/profiler-sampling-method-data-views.md)