---
title: Profiler komut satırını kullanarak bir hizmet için eşzamanlılık verileri toplama | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 275aacba-b2af-4d34-8931-ee30d777a256
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0a8d5d646df224f546d338ac7a9b474cafe8902c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690643"
---
# <a name="collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line"></a>Profil Oluşturucu Komut Satırını Kullanarak bir Hizmet için Eşzamanlılık Verileri Toplama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Profiler komut satırını kullanarak bir hizmet için eşzamanlılık verileri toplama](https://docs.microsoft.com/visualstudio/profiling/collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line).  
  
Eşzamanlılık yöntemi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] profil oluşturma araçları, kaynak Çekişme verisi ve gösterir, CPU kullanımı, iş parçacığı Çekişme, iş parçacığı geçişi, eşitleme gecikmeleri, çakışan g/ç ve diğer alanlar, iş parçacığı etkinlik verileri toplamanıza olanak sağlar sistem olayları.  
  
> [!NOTE]
>  Windows 8 ve Windows Server 2012'deki Gelişmiş güvenlik özellikleri Visual Studio profil oluşturucu bu platformlarda veri toplayan bir şekilde önemli değişiklikler gerekmiştir. Windows Store apps ayrıca yeni toplama teknikleri gerektirir. Bkz: [Windows 8 ve Windows Server 2012 uygulamalarında performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Ortak Görevler  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Çalışan bir .NET hizmetine ekleme**|-   [Nasıl yapılır: eşzamanlılık verileri toplamak için bir .NET hizmetine Profiler ekleme](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
|**Katman etkileşim verileri ekleme**|-   [Katman etkileşim verileri toplama](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**Çalışan bir C/C++ hizmetine ekleme**|-   [Nasıl yapılır: eşzamanlılık verileri toplamak için yerel bir hizmet için Profiler ekleme](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
  
## <a name="related-tasks"></a>İlişkili görevler  
  
### <a name="profiling-windows-services"></a>Windows Hizmetleri profil oluşturma  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Örnekleme yöntemiyle profili**|-   [Örnekleme kullanarak uygulama istatistikleri toplama](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md)|  
|**İzleme metodunu kullanarak profili**|-   [İzleme kullanarak ayrıntılı zamanlama verileri toplama](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method-from-the-profiler-command-line.md)|  
|**Profile.NET bellek ayırma ve atık toplama**|-   [.NET bellek verileri toplama](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
  
### <a name="profiling-concurrency-data"></a>Profil oluşturma verisi eşzamanlılık  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Bağımsız uygulamalar profili**|-   [Eşzamanlılık verileri toplama](../profiling/collecting-concurrency-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**ASP.NET Web uygulamalarının profilini oluşturma**|-   [Eşzamanlılık verileri toplama](../profiling/collecting-concurrency-data-for-an-aspnet-web-application-using-the-profiler-command-line.md)|  
  
### <a name="analyzing-concurrency-data-views-and-reports"></a>Eşzamanlılık verilerini analiz etme, görünümleri ve raporlar  
 [Kaynak Çakışması Veri Görünümleri](../profiling/resource-contention-data-views.md)  
  
 [Eşzamanlılık görselleştiricisi](../profiling/concurrency-visualizer.md)  
  
## <a name="reference"></a>Başvuru  
 [Komut satırı profil araçları başvurusu](../profiling/command-line-profiling-tools-reference.md)



