---
title: Bağımsız uygulamaların komut satırı profili oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profillng tools,stand-alone applications
- profling stand-alone applications
ms.assetid: a47f2bf2-186d-4120-bb79-34e2f3a1ee42
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b2e1ca6816a0c2d65d00e29c0e7c350f80aa8f50
ms.sourcegitcommit: 37144589d9f850ff81ec7bfb884429989925a43d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/19/2018
ms.locfileid: "34335859"
---
# <a name="command-line-profiling-of-stand-alone-applications"></a>Bağımsız uygulamaların komut satırı profili oluşturma
Bu bölümdeki yordamlar ve kullanarak tek başına (istemci) uygulamaları için performans verilerini toplamak için seçenekleri açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] komut satırından profil oluşturma araçları.  
  
## <a name="common-tasks"></a>Ortak görevler  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Uygulama istatistikleri toplamak:** performans istatistikleri toplamak için örnekleme yöntemini kullanın. Veri örnekleme, CPU kullanım sorunları çözümlemek için ve bir uygulamanın genel performans özelliklerini anlamak için kullanışlıdır.|-   [Örnekleme kullanarak uygulama istatistikleri toplama](../profiling/collecting-application-statistics-for-stand-alone-applications.md)|  
|**Ayrıntılı zamanlama verileri toplama:** ayrıntılı zamanlama bilgilerini toplamak için izleme metodunu kullanın. İzleme verileri uygulama senaryoları ayrıntılı analizini ve g/ç sorunlarını çözümleme için yararlıdır.|-   [İzleme kullanarak ayrıntılı zamanlama verileri toplama](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application.md)|  
|**.NET bellek verileri toplamak:** kullanım örnekleme veya sayısı ve boyutu gösterir .NET bellek ayırma verileri toplamak için araçları ayrılmış nesneleri. Ayrıca, her çöp koleksiyonu oluşturma geri kazanılır nesnelerinin sayısı ve boyutu gösteren nesne yaşam verisi toplayabilirsiniz.|-   [.NET Framework bellek verileri toplama](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications.md)|  
|**Eşzamanlılık verileri toplamak:** kaynak çakışması veri ve gösterir, CPU kullanımı, iş parçacığı Çekişme, iş parçacığı geçiş, eşitleme gecikmeler, alanları çakışan g/ç ve diğer iş parçacığı etkinliği verilerini toplamak için eşzamanlılık yöntemini kullanın sistem olayları.|-   [Eşzamanlılık verileri toplama](../profiling/collecting-concurrency-data-for-stand-alone-applications.md)|  
|**Katman etkileşim verileri ekleme:** zaman uyumlu ADO.NET ilgili performans verileri çağrıları, bir Microsoft yapılan uygulama ekleyebileceğiniz [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] veritabanı. Profil oluşturma çalışmaya katman etkileşim verileri ekleme belirli yordamları profil oluşturma araçları komut satırıyla gerektirir.|-   [Katman etkileşim verileri toplama](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**Deneyin:** örnekleme veya izleme yöntemini kullanarak örnek bir istemci uygulama profili için adım adım yordamları kullanın.|-   [İzlenecek yol: Komut satırı kullanarak profil örnekleme](../profiling/walkthrough-command-line-profiling-using-sampling.md)<br />-   [İzlenecek yol: İzleme kullanarak komut satırı profili oluşturma](../profiling/walkthrough-command-line-profiling-using-instrumentation.md)|  

  
## <a name="related-tasks"></a>İlişkili görevler  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Profil ASP.NET uygulamaları**|-   [Profil ASP.NET web uygulamaları](../profiling/command-line-profiling-of-aspnet-web-applications.md)|  
|**Profil Hizmetleri**|-   [Profil Hizmetleri](../profiling/command-line-profiling-of-services.md)|