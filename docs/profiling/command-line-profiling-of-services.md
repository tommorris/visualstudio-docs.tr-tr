---
title: Komut satırı hizmetler profili oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling toos,services
- profiling services
ms.assetid: f0d62318-b0e8-49c6-9a30-9f7a6adef2f6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aeb738d9a994d617c5960a9be2aacca53f338188
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="command-line-profiling-of-services"></a>Komut Satırından Hizmetler Profili Oluşturma
Bu bölümdeki yordamları ve kullanarak Windows Hizmetleri için performans verilerini toplamak için seçenekleri açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] komut satırından profil oluşturma araçları.  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Ortak Görevler  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Uygulama istatistikleri toplamak:** performans istatistikleri toplamak için örnekleme yöntemini kullanın. Veri örnekleme, CPU kullanım sorunları çözümlemek için ve bir uygulamanın genel performans özelliklerini anlamak için kullanışlıdır.|-   [Örnekleme kullanarak uygulama istatistikleri toplama](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md)|  
|**Ayrıntılı zamanlama verileri toplama:** ayrıntılı zamanlama bilgilerini toplamak için izleme metodunu kullanın. İzleme verileri uygulama senaryoları ayrıntılı analizini ve g/ç sorunlarını çözümleme için yararlıdır.|-   [İzleme kullanarak ayrıntılı zamanlama verileri toplama](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method-from-the-profiler-command-line.md)|  
|**.NET bellek verileri toplamak:** kullanım örnekleme veya sayısı ve boyutu gösterir .NET bellek ayırma verileri toplamak için araçları ayrılmış nesneleri. Ayrıca, her çöp koleksiyonu oluşturma geri kazanılır nesnelerinin sayısı ve boyutu gösteren nesne yaşam verisi toplayabilirsiniz.|-   [.NET bellek verileri toplama](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
|**Eşzamanlılık verileri toplamak:** kaynak çakışması veri ve gösterir, CPU kullanımı, iş parçacığı Çekişme, iş parçacığı geçiş, eşitleme gecikmeler, alanları çakışan GÇ ve diğer iş parçacığı etkinliği verilerini toplamak için eşzamanlılık yöntemini kullanın sistem olayları.|-   [Eşzamanlılık verileri toplama](../profiling/collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line.md)|  
|**Katman etkileşim verileri ekleme:** zaman uyumlu ADO.NET ilgili performans verileri, bir Microsoft yapılan hizmet çağırır ekleyebilirsiniz [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] veritabanı.|-   [Katman etkileşim verileri toplama](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
  
## <a name="related-tasks"></a>İlgili görevleri  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Profil tek başına (istemci) uygulamaları**|-   [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)|  
|**Profil ASP.NET uygulamaları**|-   [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)|