---
title: ".NET bellek ayırma ve yaşam süresi verilerini toplama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET memory profiling method
- Profiling Tools,.NET memory method
ms.assetid: 62a6dd5f-db66-4456-9d57-f8913dbfe4d5
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e31c9c065f7e285e76d85bbcd901d3a9c23cba6a
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="collecting-net-memory-allocation-and-lifetime-data"></a>.NET Bellek Ayırma ve Yaşam Süresi Verilerini Toplama
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].NET bellek ayırma koleksiyonunu destek profil oluşturma araçları ve yardımcı olan nesne yaşam verisi uygulamanızda bellekle ilgili performans sorunlarını algılamak.  
  
-   .NET bellek ayırma ile ilgili veriler ayrılan .NET Framework bellek nesnelerinin sayısı ve boyutu içerir.  
  
-   Nesne yaşam verisi üç atık toplama kuşakta geri kazanılan .NET Framework bellek nesnelerinin sayısı ve boyutu içerir.  
  
 **Gereksinimler**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
 Örnekleme veya izleme profili oluşturma yöntemi kullanarak verileri toplayabilir.  
  
-   Örnekleme yöntemi kullandığınızda, profil oluşturucu tüm .NET bellek ayırma ve başlatıldı veya bağlı işlem tarafından oluşturulan nesneleri izler.  
  
-   İzleme yöntemi kullandığınızda, profil oluşturucu yalnızca .NET bellek ayırma ve Araçlı modülleri tarafından oluşturulan nesneleri izler.  
  
> [!IMPORTANT]
>  .NET bellek verileri (ayırmalar, nesne yaşam süresi veya her ikisi de) örnekleme yöntemini kullanarak topladığınız tüm kullanıcı tarafından belirtilen örnekleme olayları göz ardı edilir ve uygun bellek ayırma olaylar verilerini toplamak için kullanılır.  
  
 Profil oluşturma of.NET bellek ayırma etkinleştirirseniz, ayrıca ayırma görünümü etkinleştirin. Profil oluşturma .NET yaşam süresi verilerini etkinleştirirseniz, ayrıca nesne ömrü görünümü etkinleştirin. Daha fazla bilgi için bkz: [ayırmalar görünümü](../profiling/dotnet-memory-allocations-view.md) ve [nesne ömrü görünümü](../profiling/object-lifetime-view.md).  
  
 Profil oluşturma araçları komut satırı araçlarını kullanarak .NET bellek verileri toplama hakkında daha fazla bilgi için bkz: kullanarak .NET bellek yöntemleri toplamak bellek ayırma ve nesne yaşam verisi [profil oluşturma yöntemleri gelen komut satırını kullanarak](../profiling/using-profiling-methods-to-collect-performance-data-from-the-command-line.md).  
  
### <a name="to-collect-net-memory-data"></a>.NET bellek verileri toplamak için  
  
1.  İçinde **performans Gezgini**, performans oturumu sağ tıklatın ve ardından **özellikleri**.  
  
2.  Üzerinde *Performans oturumunu***özellik sayfaları** iletişim kutusu, tıklatın **genel** sekmesini tıklatın ve seçin **toplamak .NET nesne ayırma bilgileri** onay kutusu.  
  
3.  .NET nesne yaşam süresi verilerini toplamak için seçin **ayrıca .NET nesne ömrü bilgileri toplamak** onay kutusu.  
  
## <a name="common-tasks"></a>Ortak Görevler  
 Ek seçenekler belirtebilirsiniz *Performans oturumunu***özellik sayfaları** performans oturumunun iletişim kutusu. Bu iletişim kutusunu açmak için:  
  
-   İçinde **performans Gezgini**, performans oturumu adına sağ tıklayın ve ardından **özellikleri**.  
  
 Aşağıdaki tabloda yer alan görevler, belirtebilirsiniz seçenekleri açıklanmıştır *Performans oturumunu***özellik sayfaları** .NET bellek verileri toplamak, iletişim kutusu.  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|Üzerinde **genel** sayfasında, oluşturulan profil oluşturma veri (.vsp) dosyası adlandırma ayrıntılarını belirtin.|-   [.NET bellek ayırma ve yaşam süresi verilerini toplama](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />-   [Nasıl yapılır: performans veri dosyası adlandırma seçeneklerini ayarlama](../profiling/how-to-set-performance-data-file-name-options.md)|  
|Üzerinde **başlatma** sayfasında, birden çok .exe proje kodunu çözümünüzde varsa başlatmak için uygulamayı seçin.|-   [Katman etkileşim verileri toplama](../profiling/collecting-tier-interaction-data.md)|  
|Üzerinde **katman etkileşim** sayfasında, çalıştırmak profil ADO.NET çağrısı veri ekleyin.|-   [Katman etkileşim verileri toplama](../profiling/collecting-tier-interaction-data.md)|  
|Üzerinde **Windows olaylarını** sayfasında, örnekleme verileri toplamak için bir veya daha fazla olay izleme için Windows (ETW) olayları belirtin.|-   [Nasıl yapılır: Windows (ETW) toplamak için olay izleme](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)|  
|Üzerinde **Windows sayaçları** sayfasında, profil oluşturma verileri işaretleri olarak eklemek için bir veya daha fazla işletim sistemi performans sayaçları belirtin.|-   [Nasıl yapılır: Windows sayaç verileri toplama](../profiling/how-to-collect-windows-counter-data.md)|  
|Üzerinde **Gelişmiş** sayfasında, birden çok sürümü, uygulama modülleri kullanırsanız, profil için .NET Framework çalışma zamanı sürümü belirtin. Varsayılan olarak yüklenen ilk sürüm profili.|-   [Nasıl yapılır: .NET Framework çalışma zamanı belirtin](../profiling/how-to-specify-the-dotnet-framework-runtime.md)|  
  
## <a name="instrumentation-tasks"></a>İzleme görevleri  
 Aşağıdaki tabloda yer alan görevler seçeneklerdir **özellik sayfaları** profil oluşturma araçları yöntemi ile belirli iletişim kutusu.  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|Üzerinde **ikili dosyaları** sayfasında, modüllerin Araçlı kopyaları için bir konum belirtin. Varsayılan olarak, tamamlanmış bir yedekleme klasörüne taşınır.|-   [Nasıl yapılır: izleme eklenmiş ikili dosyaları yeniden konumlandırma](../profiling/how-to-relocate-instrumented-binaries.md)|  
|Üzerinde **Araçları** sayfasında, ek yükü, profili oluşturma profili ASP.NET Web sayfalarında JavaScript kodu azaltmak için profil kısa işlevleri dışlama ve öncesinde ve sonrasında bir komut isteminde çalıştırmak için komutları belirtin izleme işlemi.|-   [Nasıl yapılır: hariç tutma veya kısa işlevleri izlemeden içerir](../profiling/how-to-exclude-or-include-short-functions-from-instrumentation.md)<br />-   [Nasıl yapılır: Web sayfalarında JavaScript kodu profili](../profiling/how-to-profile-javascript-code-in-web-pages.md)<br />-   [Nasıl yapılır: ön ve son izleme komutları belirtme](../profiling/how-to-specify-pre-and-post-instrument-commands.md)|  
|Üzerinde **CPU sayaçları** sayfasında, profil oluşturma veri eklemek için bir veya daha fazla işleyici performans sayaçları belirtin.|-   [Nasıl yapılır: CPU sayaç verileri toplama](../profiling/how-to-collect-cpu-counter-data.md)|  
|Üzerinde **Gelişmiş** sayfasında, tüm ek VSInstr.exe seçenekleri, dahil etmek veya hariç belirli işlevleri gibi seçeneklerini istediğinizi belirtin. Vsınstr seçenekleri hakkında daha fazla bilgi için bkz: [Vsınstr](../profiling/vsinstr.md)|-   [Nasıl yapılır: ek izleme seçeneklerini belirtme](../profiling/how-to-specify-additional-instrumentation-options.md)<br />-   [Nasıl yapılır: belirli işlevler için araçları sınırlama](../profiling/how-to-limit-instrumentation-to-specific-functions.md)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)   
 [Nasıl yapılır: Koleksiyon yöntemleri seçme](../profiling/how-to-choose-collection-methods.md)   
 [Performans oturum özellikleri](../profiling/performance-session-properties.md)