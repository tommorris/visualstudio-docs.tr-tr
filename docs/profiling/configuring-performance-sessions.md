---
title: Performans oturumlarını yapılandırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- common tasks, performance
- common tasks, profiling tools
- profiling tools, common tasks
- performance, gathering data
ms.assetid: e1c3ba41-ffca-4edf-9a7f-8a5a9244ef9b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 85155bb357f808b477d9d6041c16cdc2d0f3681b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="configuring-performance-sessions"></a>Performans Oturumlarını Yapılandırma
Kullanarak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları, çok çeşitli çok sayıda uygulama türleri için performans verilerini toplayabilir. Bu bölümde Performans oturumunu ve hedef ikili performans Wizardand özelliklerini ilginizi çeken verileri toplamak için profil oluşturma araçları yapılandırmak için nasıl kullanılacağını gösterir. Profil oluşturma araçları yapılandırma özellikleri de profil çalıştırılmasıyla toplanan veri miktarını denetlemek için kullanılabilir. Daha fazla bilgi için bkz: [denetleme veri toplama](../profiling/controlling-data-collection.md).  
  
> [!NOTE]
>  Çoğu durumda, performans Sihirbazı'nı varsayılan özelliklerini kullanarak profil oluşturma verileri toplama etkili bir yoldur. Daha fazla bilgi için bkz: [performans profili oluşturma Başlangıç Kılavuzu](../profiling/beginners-guide-to-performance-profiling.md) ve [Başlarken](../profiling/getting-started-with-performance-tools.md).  
  
## <a name="common-tasks"></a>Ortak Görevler  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Temel profil oluşturma seçenekleri ayarlayın:** yapılandırmanız gerekir [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] Microsoft Simge sunucusunu kullanmak için. Bu simge, Windows ve diğer Microsoft uygulamaları geçerli sürümü için işlevi ve parametre adları gibi erişebildiğinizden emin hale getirir. Profil Araçları ve profil oluşturma veri dosyalarıyla adları sistem izinleri gibi bir profil oluşturma oturumu başlatılmadan önce diğer genel seçenekleri de belirtebilirsiniz.|-   [Nasıl yapılır: başvuru pencereleri sembol bilgileri](../profiling/how-to-reference-windows-symbol-information.md)<br />-   [Nasıl yapılır: sembol bilgilerini serileştirme](../profiling/how-to-serialize-symbol-information.md)<br />-   [Nasıl yapılır: geçerli oturum ayarlayın](../profiling/how-to-set-the-current-session.md)<br />-   [Nasıl yapılır: izinleri ayarla](../profiling/how-to-set-permissions.md)<br />-   [Nasıl yapılır: performans veri dosyası adlandırma seçeneklerini ayarlama](../profiling/how-to-set-performance-data-file-name-options.md)|  
|**Toplamak istediğiniz verileri belirtin:** profil oluşturma oturumu yapılandırmak için kullandığınız yordam profil oluşturmayı istediğiniz hedef uygulama türü ve toplamak istediğiniz performans veri türüne bağlıdır.|-   [Nasıl yapılır: Koleksiyon yöntemleri seçme](../profiling/how-to-choose-collection-methods.md)<br />-   [Örnekleme kullanarak performans istatistikleri toplama](../profiling/collecting-performance-statistics-by-using-sampling.md)<br />-   [.NET bellek ayırma ve yaşam süresi verilerini toplama](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />-   [İzleme kullanarak ayrıntılı zamanlama verileri toplama](../profiling/collecting-detailed-timing-data-by-using-instrumentation.md)<br />-   [Nasıl yapılır: Web sayfalarında JavaScript kodu profili](../profiling/how-to-profile-javascript-code-in-web-pages.md)<br />-   [İş parçacığı ve işlem eşzamanlılık verileri toplama](../profiling/collecting-thread-and-process-concurrency-data.md)<br />-   [Ek performans verileri toplama](../profiling/collecting-additional-performance-data.md)|  
|**Gelişmiş yapılandırma seçenekleri ayarlayın:** ortak dil çalışma zamanı (CLR) birden fazla sürümünü yükleme .NET Framework uygulamaları profili oluşturduğunuzda, profil için hangi sürümün belirtebilirsiniz. Bir performans oturumunda birden çok .exe dosyaları varsa, ikili dosyaları başlangıç sırasını ayarlayabilirsiniz.|-   [Nasıl yapılır: .NET Framework çalışma zamanı belirtin](../profiling/how-to-specify-the-dotnet-framework-runtime.md)<br />-   [Nasıl yapılır: başlatma için ikili dosya belirtme](../profiling/how-to-specify-the-binary-to-start.md)|  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Veri toplama denetimi](../profiling/controlling-data-collection.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans Gezgini](../profiling/performance-explorer.md)