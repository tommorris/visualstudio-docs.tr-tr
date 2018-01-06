---
title: "Örnekleme kullanarak performans istatistikleri toplama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Profiling Tools,sampling
- sampling profiling method
ms.assetid: 8e36361b-bb3d-40c6-b286-0e68c0ecb915
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4131bfc5bd361e4d2ac4aeca0c4f7003f975d462
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="collecting-performance-statistics-by-using-sampling"></a>Örnekleme Kullanarak Performans İstatistikleri Toplama
Varsayılan olarak, [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)] profil oluşturma araçları örnekleme yöntemini profil bilgilerini 10,000,000 her işlemci döngülerinin (yaklaşık her yüzde saniyede bir 1 GHz bilgisayarda) toplar. Örnekleme yöntemi işlemci kullanım sorunları bulmak için yararlıdır ve çoğu performans araştırmalar başlatmak için önerilen yöntemdir.  
  
 **Gereksinimler**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
 Aşağıdaki yordamlardan birini kullanarak örnekleme yöntemini belirtebilirsiniz:  
  
-   Profil Oluşturma Sihirbazı'nın ilk sayfasında, tıklatın **CPU örnekleme (önerilir)**.  
  
-   Üzerinde **performans Gezgini** araç, **yöntemi** tıklatın **örnekleme**.  
  
-   Üzerinde **genel** sayfa performans oturumu için Özellikler iletişim kutusunda tıklatın **örnekleme**.  
  
## <a name="common-tasks"></a>Ortak Görevler  
 Ek seçenekler belirtebilirsiniz *Performans oturumunu***özellik sayfaları** performans oturumunun iletişim kutusu. Bu iletişim kutusunu açmak için:  
  
-   İçinde **performans Gezgini**, performans oturumu adına sağ tıklayın ve ardından **özellikleri**.  
  
 Aşağıdaki tabloda yer alan görevler, belirtebilirsiniz seçenekleri açıklanmıştır *Performans oturumunu***özellik sayfaları** örnekleme yöntemini kullanarak profil, iletişim kutusu.  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|Üzerinde **genel** sayfasında .NET bellek ayırma ve yaşam süresi verilerini toplama ekleyin ve oluşturulan profil oluşturma veri (.vsp) dosyası adlandırma ayrıntılarını belirtin.|-   [.NET bellek ayırma ve yaşam süresi verilerini toplama](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />-   [Nasıl yapılır: performans veri dosyası adlandırma seçeneklerini ayarlama](../profiling/how-to-set-performance-data-file-name-options.md)|  
|Üzerinde **örnekleme** sayfasında, örnekleme hızını değiştirmek, örnekleme olayı işlemci saat döngüsü başka bir işlemci performans sayacı değiştirmek veya her ikisi de Değiştir...|-   [Nasıl yapılır: örnekleme olayları seçme](../profiling/how-to-choose-sampling-events.md)|  
|Üzerinde **başlatma** sayfasında, uygulamayı başlatmak için ve başlangıç sipariş kod çözümünüz içinde birden çok .exe proje olup olmadığını belirtin.|-   [Katman etkileşim verileri toplama](../profiling/collecting-tier-interaction-data.md)|  
|Üzerinde **katman etkileşim** sayfasında, çalıştırmak theprofiling içinde toplanan veriler ADO.NET çağrı bilgileri ekleyin.|-   [Katman etkileşim verileri toplama](../profiling/collecting-tier-interaction-data.md)|  
|Üzerinde **Windows olaylarını** sayfasında, örnekleme verileri toplamak için bir veya daha fazla olay izleme için Windows (ETW) olayları belirtin.|-   [Nasıl yapılır: Windows (ETW) toplamak için olay izleme](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)|  
|Üzerinde **Windows sayaçları** sayfasında, profil oluşturma verileri işaretleri olarak eklemek için bir veya daha fazla işletim sistemi performans sayaçları belirtin.|-   [Nasıl yapılır: Windows sayaç verileri toplama](../profiling/how-to-collect-windows-counter-data.md)|  
|Üzerinde **Gelişmiş** sayfasında, birden çok sürümü, uygulama modülleri kullanırsanız, profil için .NET Framework çalışma zamanı sürümü belirtin. Varsayılan olarak yüklenen ilk sürüm profili.|-   [Nasıl yapılır: .NET Framework çalışma zamanı belirtin](../profiling/how-to-specify-the-dotnet-framework-runtime.md)|