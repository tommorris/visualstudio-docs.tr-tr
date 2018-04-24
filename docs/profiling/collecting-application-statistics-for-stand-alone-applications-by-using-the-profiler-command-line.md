---
title: Profil oluşturucu komut satırını kullanarak bağımsız uygulamalar için uygulama istatistikleri toplama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- sampling profiling method
- profilng tools,sampling method
ms.assetid: be2dbdd0-fc88-45f9-a1d5-bcb4f64e17ad
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d1d102629c2a99c5ddf2e79809e58a76c96f1f79
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="collecting-application-statistics-for-stand-alone-applications-by-using-the-profiler-command-line"></a>Profil Oluşturucu Komut Satırını Kullanarak Bağımsız Uygulamalar için Uygulama İstatistikleri Toplama
Bu bölümde, yordamlar ve komut satırından örnekleme yöntemini kullanarak bir istemci (tek başına) uygulaması için performans istatistikleri toplamak için seçenekleri açıklar.  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Ortak Görevler  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Profil oluşturma kullanarak uygulama başlatma**|-   [Nasıl yapılır: bağımsız bir uygulama başlatma ve uygulama istatistikleri toplama](../profiling/how-to-launch-a-stand-alone-application-with-the-profiler-and-collect-application-statistics-by-using-the-command-line.md)|  
|**Çalışan bir .NET Framework uygulamasına profil oluşturucu ekleme**|-   [Nasıl yapılır: profil oluşturucuyu bir .NET Framework uygulamasına ekleme ve uygulama istatistikleri toplama](../profiling/how-to-attach-the-profiler-to-a-dotnet-framework-stand-alone-application-and-collect-application-statistics-by-using-the-command-line.md)|  
|**Bir çalışan C/C++ uygulamasına profil oluşturucu ekleme**|-   [Nasıl yapılır: yerel bir uygulamaya profil oluşturucu ekleme ve uygulama istatistikleri toplama](../profiling/how-to-attach-the-profiler-to-a-native-stand-alone-application-and-collect-application-statistics-by-using-the-command-line.md)|  
|**Katman etkileşim verileri ekleme**|-   [Katman etkileşim verileri toplama](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
  
## <a name="related-tasks"></a>İlgili görevleri  
  
### <a name="profiling-stand-alone-applications"></a>Bağımsız Uygulamaların Profilini Oluşturma  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Bir uygulamayı izleme**|-   [İzleme kullanarak ayrıntılı zamanlama verileri toplama](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application-by-using-the-profiler-command-line.md)|  
|**.NET bellek ayırma ve atık toplama verileri toplama**|-   [.NET Framework bellek verileri toplama](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Kaynak çakışması ve iş parçacığı yürütme verilerini toplama**|-   [Eşzamanlılık verileri toplama](../profiling/collecting-concurrency-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
  
### <a name="profiling-by-using-the-sampling-method"></a>Örnekleme yöntemini kullanarak profil oluşturma  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**ASP.NET Web uygulamalarında profil**|-   [Örnekleme kullanarak uygulama istatistikleri toplama](../profiling/collecting-application-statistics-for-aspnet-web-applications-using-the-profiler-sampling-method-from-the-command-line.md)|  
|**Profil Hizmetleri**|-   [Örnekleme kullanarak uygulama istatistikleri toplama](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md). Örnekleme yöntemini kullanarak Windows hizmetlerinden performans istatistikleri toplamak açıklar.|  
  
### <a name="analyzing-sampling-data-views-and-reports"></a>Görünümler ve raporlar örnekleme verileri analiz etme  
 [Örnekleme yöntemi veri görünümleri](../profiling/profiler-sampling-method-data-views.md)