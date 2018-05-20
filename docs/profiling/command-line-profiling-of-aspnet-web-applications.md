---
title: ASP.NET Web uygulamalarının komut satırı profili oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling ASP.NET applications
- profling tools,ASP.NET applications
ms.assetid: 897c00d5-5767-433b-a960-4a29c6023ede
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 6c5b97460defeaa22ad20e9a1ff4be38514b020a
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="command-line-profiling-of-aspnet-web-applications"></a>ASP.NET web uygulamalarının komut satırı profili oluşturma
Bu bölümde yordamlar ve performans verilerini toplamak için seçenekleri açıklar [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulamaları kullanarak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] komut satırından profil oluşturma araçları.  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Ortak görevler
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Profil oluşturma verilerini kolayca temel ASP.NET Topla:** kullanım **VSPerfASPNETCmd** toplamak örnekleme, izleme, .NET bellek, çakışma veya yapılandırma gereksinimleri olmadan etkileşim veri katmanı için aracı ve İçin gerekli olan Internet Information Services (IIS) yeniden **VSPerfCmd**. **VSPerfASPNETCmd** ek veri toplamak veya veri toplama denetlemek için izin vermez. **Not:****VSPerfASPNETCmd** kullanmayı tercih edilen aracı profili ASP.NET Web siteleri için bağımsız profil oluşturucu kullanın.|-   [Profil oluşturma VSPerfASPNETCmd ile hızlı web sitesi](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)|  
|**Uygulama istatistikleri toplamak:** performans istatistikleri toplamak için örnekleme yöntemini kullanın. Veri örnekleme, CPU kullanım sorunları çözümlemek için ve bir uygulamanın genel performans özelliklerini anlamak için kullanışlıdır.|-   [Örnekleme kullanarak uygulama istatistikleri toplama](../profiling/collecting-application-statistics-for-aspnet-using-the-profiler-sampling-method.md)|  
|**Ayrıntılı zamanlama verileri toplama:** ayrıntılı zamanlama bilgilerini toplamak için izleme metodunu kullanın. İzleme verileri uygulama senaryoları ayrıntılı analizini ve g/ç sorunlarını çözümleme için yararlıdır.|-   [İzleme kullanarak ayrıntılı zamanlama verileri toplama](../profiling/collecting-detailed-timing-data-aspnet-profiler-instrumentation-method.md)|  
|**.NET bellek verileri toplamak:** kullanım örnekleme veya sayısı ve boyutu gösterir .NET bellek ayırma verileri toplamak için araçları ayrılmış nesneleri. Ayrıca, her çöp koleksiyonu oluşturma geri kazanılır nesnelerinin sayısı ve boyutu gösteren nesne yaşam verisi toplayabilirsiniz.|-   [Bellek verileri toplama](../profiling/collecting-memory-data-from-an-aspnet-web-application.md)|  
|**Eşzamanlılık verileri toplamak:** kaynak çakışması veri toplamak için eşzamanlılık yöntemi kullanın. **Not:** iş parçacığı etkinliği ve görselleştirme veri toplamayı Web uygulamaları için desteklenmiyor.|-   [Eşzamanlılık verileri toplama](../profiling/collecting-concurrency-data-for-an-aspnet-web-application.md)|  
|**Katman etkileşim verileri ekleme:** zaman uyumlu ilgili performans verileri ekleyebilirsiniz [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)] çağrısı [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması için bir Microsoft yapar [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] veritabanı.|-   [Katman etkileşim verileri toplama](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
  
## <a name="related-tasks"></a>İlişkili görevler
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Profil tek başına (istemci) uygulamaları**|-   [Bağımsız uygulamalar profili](../profiling/command-line-profiling-of-stand-alone-applications.md)|  
|**Profil Hizmetleri**|-   [Profil Hizmetleri](../profiling/command-line-profiling-of-services.md)|