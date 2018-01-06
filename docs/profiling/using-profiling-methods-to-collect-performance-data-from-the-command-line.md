---
title: "Komut satırından performans verilerini toplamak için profil oluşturma yöntemlerini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5613fafc-f298-4e7a-9a2d-a853b61cdf9c
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e7acfa376ea805553b931925a2fac0a33b44bb83
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="using-profiling-methods-to-collect-performance-data-from-the-command-line"></a>Komut Satırından Performans Verileri Toplamak için Profil Oluşturma Yöntemlerini Kullanma
Tercih ettiğiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları komut satırı araçları ve seçenekleri etkenlere bağlıdır tür bir uygulama gibi profil olduğunu, kullanmak istediğiniz ve olup hedef uygulama yazılmış yerel ya da Profiloluşturmayöntemi[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]kodu.  
  
 Bu konu, komut satırı yordam konularını seçtiğiniz profil yönteme göre düzenler.  
  
## <a name="in-this-topic"></a>Bu konuda  
 [Performans istatistikleri toplamak için örnekleme yöntemini kullanarak](#BKMK_Using_the_sampling_method_to_collect_performance_statistics)  
  
 [Ayrıntılı zamanlama verileri toplamak için izleme metodunu kullanarak](#BKMK_Using_the_instrumentation_method_to_collect_detailed_timing_data)  
  
 [Bellek ayırma ve nesne yaşam süresi verilerini toplamak için .NET bellek yöntemlerini kullanma](#BKMK_Using__NET_memory_methods_to_collect_memory_allocation_and_object_lifetime_data)  
  
 [Kaynak çakışması ve iş parçacığı etkinliği verilerini toplamak için eşzamanlılık yöntemini kullanarak](#BKMK_Using_the_concurrency_method_to_collect_resource_contention_and_thread_activity_data)  
  
 [Profil oluşturma çalışmaya katman etkileşim verileri ekleme](#BKMK_Adding_tier_interaction_data_to_a_profiling_run)  
  
##  <a name="BKMK_Using_the_sampling_method_to_collect_performance_statistics"></a>Performans istatistikleri toplamak için örnekleme yöntemini kullanarak  
 Profil oluşturma araçları örnekleme yöntemini profil çalıştırmada belirli aralıklarla performans verilerini toplar. Veri örnekleme CPU bağımlı performans sorunlarını Öngörüler sağlayabilir ve bir uygulamanın performansını keşfetmeye başlamak için en iyi yolu olabilir.  
  
 Profil Oluşturucu ve aynı zamanda uygulama başlatabilirsiniz veya çalışan bir örneği olan bir uygulama için profil oluşturucu ekleyebilirsiniz.  
  
|Görev|Hedef uygulama türü|  
|----------|-----------------------------|  
|**Uygulama Başlat**|-   [Bağımsız uygulamalar](../profiling/how-to-launch-a-stand-alone-application-with-the-profiler-and-collect-application-statistics-by-using-the-command-line.md)|  
|**Bir çalışan işleme iliştirilemiyor**|-   [.NET framework bağımsız uygulamalar](../profiling/how-to-attach-the-profiler-to-a-dotnet-framework-stand-alone-application-and-collect-application-statistics-by-using-the-command-line.md)<br />-   [Yerel bağımsız uygulamalar](../profiling/how-to-attach-the-profiler-to-a-native-stand-alone-application-and-collect-application-statistics-by-using-the-command-line.md)<br />-   [ASP.NET Web uygulamaları](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-application-statistics-by-using-the-command-line.md)<br />-   [.NET Hizmetleri](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-application-statistics-by-using-the-command-line.md)<br />-   [Yerel Hizmetleri](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-application-statistics-by-using-the-command-line.md)|  
  
##  <a name="BKMK_Using_the_instrumentation_method_to_collect_detailed_timing_data"></a>Ayrıntılı zamanlama verileri toplamak için izleme metodunu kullanarak  
 Profil oluşturma araçları izleme yöntemini yazılım araştırmalar kayıt performans bilgileri içeren uygulama ikili dosyaların kopyalarını performans verilerini toplar. İzleme verileri, başlangıç ve bitiş her Araçlı işlevinin ve diğer işlevleri her çağrısına Araçlı işlevden toplanır. İzleme yöntemi, disk kullanımı gibi g/ç sorunları performans sorunları bulmak için yararlıdır.  
  
 İzleme eklenmiş ikili ile oluşturduğunuz [VInstr.exe](../profiling/vsinstr.md) aracı. Profil oluşturucu başlatma sonra hedef uygulama çalıştırdığınızda, verileri izleme eklenmiş ikili dosyalar otomatik olarak toplanır.  
  
 **Hedef uygulama türü**  
  
-   [.NET framework bağımsız bileşenler](../profiling/how-to-instrument-a-stand-alone-dotnet-framework-component-and-collect-timing-data-with-the-profiler-from-the-command-line.md)  
  
-   [Yerel bağımsız bileşenler](../profiling/how-to-instrument-a-native-stand-alone-component-and-collect-timing-data-with-the-profiler-from-the-command-line.md)  
  
-   [Statik olarak derlenmiş bir ASP.NET Web uygulamaları](../profiling/how-to-instrument-a-statically-compiled-aspnet-web-application-and-collect-detailed-timing-data-with-the-profiler-by-using-the-command-line.md)  
  
-   [Dinamik olarak derlenmiş bir ASP.NET Web uygulamaları](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-detailed-timing-data-with-the-profiler-by-using-the-command-line.md)  
  
-   [.NET Hizmetleri](../profiling/how-to-instrument-a-dotnet-service-and-collect-detailed-timing-data-by-using-the-profiler-command-line.md)  
  
-   [Yerel Hizmetleri](../profiling/how-to-instrument-a-native-service-and-collect-detailed-timing-data-by-using-the-profiler-command-line.md)  
  
##  <a name="BKMK_Using__NET_memory_methods_to_collect_memory_allocation_and_object_lifetime_data"></a>Bellek ayırma ve nesne yaşam süresi verilerini toplamak için .NET bellek yöntemlerini kullanma  
 Profil oluşturma araçlar .NET bellek yöntemi toplamanızı sağlar [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] bellek ayırma verileri ve nesnelerin ömrü hakkındaki bilgileri [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].  
  
 Profil Oluşturucu kullanarak hedef uygulama başlatabilirsiniz; çalışan bir örneği olan bir uygulama için profil oluşturucu ekleyebilirsiniz; ve ayrıntılı zamanlama bilgi ile birlikte toplamak için uygulama Araçlı sürümlerini oluşturabilirsiniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] bellek verileri.  
  
|Görev|Hedef uygulama türü|  
|----------|-----------------------------|  
|**Uygulama Başlat**|-   [Bağımsız bir .NET Framework uygulamaları](../profiling/how-to-launch-a-stand-alone-dotnet-framework-application-with-the-profiler-to-collect-memory-data-by-using-the-command-line.md)|  
|**Bir çalışan işleme iliştirilemiyor**|-   [.NET framework bağımsız uygulamalar](../profiling/how-to-attach-the-profiler-to-a-dotnet-framework-stand-alone-application-to-collect-memory-data-by-using-the-command-line.md)<br />-   [ASP.NET Web uygulamaları](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-memory-data-by-using-the-command-line.md)<br />-   [.NET Hizmetleri](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-memory-data-by-using-the-command-line.md)|  
|**Gereç modülleri**|-   [.NET framework bağımsız bileşenler](../profiling/how-to-instrument-a-stand-alone-dotnet-framework-component-and-collect-memory-data-with-the-profiler-by-using-the-command-line.md)<br />-   [Statik olarak derlenmiş bir ASP.NET Web uygulamaları](../profiling/how-to-instrument-a-statically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line.md)<br />-   [Dinamik olarak derlenmiş bir ASP.NET Web uygulamaları](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line.md)<br />-   [.NET Hizmetleri](../profiling/how-to-instrument-a-dotnet-framework-service-and-collect-memory-data-by-using-the-profiler-command-line.md)|  
  
##  <a name="BKMK_Using_the_concurrency_method_to_collect_resource_contention_and_thread_activity_data"></a>Kaynak çakışması ve iş parçacığı etkinliği verilerini toplamak için eşzamanlılık yöntemini kullanarak  
 Profil oluşturma araçları eşzamanlılık yöntemi, kaynak çekişmesini ve iş parçacığı ve işlem etkinlik verileri birden çok iş parçacıklı uygulamalarda verileri toplamak sağlar.  
  
 Profil Oluşturucu kullanarak uygulamayı başlatabilirsiniz veya çalışan bir örneği olan bir uygulama için profil oluşturucu ekleyebilirsiniz.  
  
|Görev|Hedef uygulama türü|  
|----------|-----------------------------|  
|**Uygulama Başlat**|-   [Bağımsız bir .NET Framework uygulama](../profiling/how-to-launch-a-stand-alone-dotnet-framework-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line.md)<br />-   [Tek başına yerel uygulama](../profiling/how-to-launch-a-stand-alone-native-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line.md)|  
|**Bir çalışan işleme iliştirilemiyor**|-   [.NET framework bağımsız uygulamasına](../profiling/how-to-attach-the-profiler-to-a-dotnet-framework-stand-alone-application-to-collect-concurrency-data-by-using-the-command-line.md)<br />-   [Yerel tek başına uygulama](../profiling/how-to-attach-the-profiler-to-a-native-stand-alone-application-and-collect-concurrency-data-by-using-the-command-line.md)<br />-   [ASP.NET Web uygulaması](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-concurrency-data-by-using-the-command-line.md)<br />-   [.NET hizmeti](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-concurrency-data-by-using-the-command-line.md)<br />-   [Yerel hizmeti](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
  
##  <a name="BKMK_Adding_tier_interaction_data_to_a_profiling_run"></a>Profil oluşturma çalışmaya katman etkileşim verileri ekleme  
 Profil oluşturma çalışmaya katman etkileşim verileri ekleme belirli yordamları profil oluşturma araçları komut satırıyla gerektirir. Bkz: [katman etkileşim verileri toplama](../profiling/adding-tier-interaction-data-from-the-command-line.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)