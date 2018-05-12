---
title: Profil oluşturucu komut satırını kullanarak bir hizmet için eşzamanlılık verileri toplama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 275aacba-b2af-4d34-8931-ee30d777a256
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e3bd10121973c88e7a211aa741664b8ffb9b7bbc
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
---
# <a name="collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line"></a>Profil Oluşturucu Komut Satırını Kullanarak bir Hizmet için Eşzamanlılık Verileri Toplama
Eşzamanlılık yöntemi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları, kaynak çakışması veri ve gösterir, CPU kullanımı, iş parçacığı Çekişme, iş parçacığı geçiş, eşitleme gecikmeler, alanları çakışan GÇ ve diğer iş parçacığı etkinliği verilerini toplamak sağlar sistem olayları.  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Ortak Görevler  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Çalışan bir .NET hizmetine ekleme**|-   [Nasıl yapılır: eşzamanlılık verileri toplamak için bir .NET hizmetine profil oluşturucu ekleme](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
|**Katman etkileşim verileri ekleme**|-   [Katman etkileşim verileri toplama](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**Bir çalışan C/C++ hizmetine ekleme**|-   [Nasıl yapılır: eşzamanlılık verileri toplamak için bir yerel hizmete profil oluşturucu ekleme](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
  
## <a name="related-tasks"></a>İlgili görevleri  
  
### <a name="profiling-windows-services"></a>Profil oluşturma Windows Hizmetleri  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Örnekleme yöntemini kullanarak profil**|-   [Örnekleme kullanarak uygulama istatistikleri toplama](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md)|  
|**İzleme metodunu kullanarak profil**|-   [İzleme kullanarak ayrıntılı zamanlama verileri toplama](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method.md)|  
|**Profile.NET bellek ayırma ve çöp toplama**|-   [.NET bellek verileri toplama](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
  
### <a name="profiling-concurrency-data"></a>Eşzamanlılık verileri profil oluşturma  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Bağımsız uygulamalar profili**|-   [Eşzamanlılık verileri toplama](../profiling/collecting-concurrency-data-for-stand-alone-applications.md)|  
|**ASP.NET Web uygulamalarında profil**|-   [Eşzamanlılık verileri toplama](../profiling/collecting-concurrency-data-for-an-aspnet-web-application.md)|  
  
### <a name="analyzing-concurrency-data-views-and-reports"></a>Görünümler ve raporlar eşzamanlılık verileri analiz etme  
 [Kaynak Çakışması Veri Görünümleri](../profiling/resource-contention-data-views.md)  
  
 [Eşzamanlılık görselleştiricisi](../profiling/concurrency-visualizer.md)  
  
## <a name="reference"></a>Başvuru  
 [Komut satırı profil araçları başvurusu](../profiling/command-line-profiling-tools-reference.md)