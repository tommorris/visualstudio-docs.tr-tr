---
title: "Windows 8 ve Windows Server 2012 uygulamaların performans araçları | Microsoft Docs"
ms.custom: 
ms.date: 06/19/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a704215d-d252-4087-921b-ac81ebe2a9c9
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 83bd33e6da9795a7e4e638fa91612e930a882cb0
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2017
---
# <a name="performance-tools-on-windows-8-and-windows-server-2012-applications"></a>Windows 8 ve Windows Server 2012 uygulamaların performans araçları
Windows 8 ve Windows Server 2012'de başlangıç Gelişmiş güvenlik özellikleri şekilde Visual Studio performans araçları de yapılan önemli değişiklikler bu platformlarda veri toplama gereklidir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bu konu, Windows 8 ve Windows Server 2012 platformlarda itibaren performans araçları için değişiklikleri açıklar.
  
> [!NOTE]
>  Performans araçları Windows (Windows 7, Windows Server 2008 R2), desteklenen diğer sürümleri için değişmemiştir.
  
##  <a name="BKMK_In_this_topic"></a>Bu konudaki  
 [Visual Studio IDE'den UWP uygulamaları veri toplama](#BKMK_Profiling_Windows_Store_apps_from_the_Visual_Studio_IDE)  
  
 [Windows 8 masaüstünde veya Windows Server 2012 Visual Studio IDE üzerinden çalışan uygulamalar üzerinde verileri toplama](#BKMK_Profiling_apps_running_on_the_Windows_8_desktop_or_on_Windows_Server_2012_from_the_Visual_Studio_IDE)  
  
-   [Visual Studio IDE'den örnekleme kullanarak Windows Server 2012 veya Windows 8 Masaüstü üzerinde çalışan uygulamalar üzerinde verileri toplama](#BKMK_Profiling_apps_running_on_the_Windows_8_desktop_or_on_Windows_Server_2012_by_using_sampling_from_the_Visual_Studio_IDE)  
  
 [Komut satırından profil oluşturma](#BKMK_Profiling_from_the_command_line)  
  
 [Katman etkileşim (TIP) verileri toplama](#BKMK_Collecting_tier_interaction__TIP__data)  
  
##  <a name="BKMK_Profiling_Windows_Store_apps_from_the_Visual_Studio_IDE"></a>Visual Studio IDE'den UWP uygulamaları veri toplama  
 JavaScript ve HTML 5'te yazılmış bir UWP uygulaması profil, JavaScript kodu için izleme verileri toplayın. Bir UWP uygulaması veya Visual C++, Visual C# veya Visual Basic yazılmış bileşeni profil için yerel ve yönetilen kod için örnekleme veri toplama. Uygulamanızı yerel olarak veya bir uzak makinede profil.  
  
 Bu profil özellikleri ve seçenekleri UWP uygulamaları profil olduğunda desteklenmez:  
  
-   Örnekleme yöntemini kullanarak JavaScript uygulamaları profil oluşturma.  
  
-   İzleme metodunu kullanarak yönetilen ve yerel kodu profili oluşturma.  
  
-   Eşzamanlılık profili oluşturma  
  
-   .NET bellek profili oluşturma  
  
-   Katman etkileşimli profil oluşturma (TIP)  
  
-   Örnekleme olay ve zamanlama aralığı ayarını veya ek performans sayacı verilerini toplama gibi örnekleme seçenekleri.  
  
-   İzleme seçenekleri, performans ve windows sayaç verileri toplama veya ek komut satırı seçenekleri belirterek gibi.  
  
 UWP uygulamalar profili oluşturma hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
 [Yerel makinede UWP uygulamaları çalıştırma](../debugger/run-windows-store-apps-on-the-local-machine.md)  
  
 [Uzak makinede UWP uygulamaları çalıştırma](../debugger/run-windows-store-apps-on-a-remote-machine.md)  
  
 [Profil Araçları](profiling-tools.md)  
  
-   [JavaScript belleği](../profiling/javascript-memory.md)
  
-   [Yerel makinede UWP uygulamalarında profil Visual C++, Visual C# ve Visual Basic kodu](http://msdn.microsoft.com/en-us/2d0c939e-0bac-48c5-b727-46f6c6113060)  
  
-   [Uzak cihazda UWP uygulamalarında profil Visual C++, Visual C# ve Visual Basic kodu](http://msdn.microsoft.com/en-us/b932a2be-11b0-40fd-b996-75c6b6a79d22)  
  
-   [UWP uygulamalarında Visual C++, Visual C# ve Visual Basic kodu için performans verilerini çözümleme](http://msdn.microsoft.com/en-us/5de4a413-d924-425f-afc4-e1ecfb0fca18)  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Profiling_apps_running_on_the_Windows_8_desktop_or_on_Windows_Server_2012_from_the_Visual_Studio_IDE"></a>Windows 8 masaüstünde veya Windows Server 2012 Visual Studio IDE üzerinden çalışan uygulamalar üzerinde verileri toplama  
 İzleme metodunu kullanarak profil oluşturma Windows 8 için değişmemiştir.  
  
 Katman etkileşimli profil oluşturma (TIP) örnekleme yöntemini kullanarak desteklenmiyor.  
  
###  <a name="BKMK_Profiling_apps_running_on_the_Windows_8_desktop_or_on_Windows_Server_2012_by_using_sampling_from_the_Visual_Studio_IDE"></a>Visual Studio IDE'den örnekleme kullanarak Windows Server 2012 veya Windows 8 Masaüstü üzerinde çalışan uygulamalar üzerinde verileri toplama  
 Bu profil özellikleri ve seçenekleri, Windows 8 masaüstü uygulamalarında veya örnekleme yöntemini kullanarak Windows Server 2012 uygulamalarında profil oluşturma zaman desteklenmez:
  
-   Katman etkileşimli profil oluşturma (TIP). İpucu verilerinin toplanması araçları kullanılarak desteklenir.
  
-   Örnekleme olay ve zamanlama aralığı ayarını veya ek performans sayacı verilerini toplama gibi örnekleme Seçenekleri'ni kullanın.  
  
##  <a name="BKMK_Profiling_from_the_command_line"></a>Komut satırından profil oluşturma  
 Visual Studio yüklemesi gerekmez aygıtlar dahil olmak üzere Windows 8 ve Windows Server 2012 cihazlarda profil oluşturma verileri toplamak için iki komut satırı araçları kullanın:  
  
|Aracı adı|Açıklama|  
|---------------|-----------------|  
|[VSPerf](../profiling/vsperf.md)|UWP uygulamaları profil oluşturma verileri toplar ve Windows 8 Masaüstü uygulamaları ve Windows Server 2012 uygulamaları örnek profil oluşturma verileri toplar...|  
|[VSPerfCmd](../profiling/vsperfcmd.md)|İzleme, eşzamanlılık ve katman etkileşimli profil oluşturma Windows 8 Masaüstü veya Windows Server 2012 üzerinde çalışan uygulamalardan veri toplar. Önceki Windows sürümleri tüm profil oluşturma veri türlerini toplar.|  
  
 Her iki araçları, yerel bilgisayarda kullanmak için Visual Studio ile yüklenir.  
  
 Profil uygulama için Visual Studio yüklüyse, olmayan aşağıdakilerden birini yapın:  
  
-   Araçları Visual Studio'dan uzak araçları bir parçası olarak indirin [MSDN web sitesini](http://go.microsoft.com/fwlink/?LinkID=219549).  
  
-   Kopyalama ve Visual Studio bilgisayarınızdan bağımsız profil oluşturucu Araçlar yükleme programını çalıştırın. Yükleme programları bulunan *VSInstallDir %* **\Team Tools\Performance Tools\Setups** klasör. Uzak bilgisayarın işletim sistemi (x86/x64) için Kurulum programı seçin.  
  
> [!NOTE]
>  İpucu profil oluşturma verilerini toplamak için uzak bilgisayardaki Visual Studio makinenizden bağımsız profil oluşturucuyu yüklemeniz gerekir.  
  
 Bu profil özellikleri ve seçenekleri komut satırından Windows 8 ve Windows Server 2012 uygulamalarında profil oluşturma zaman desteklenmez:  
  
-   Örnekleme moduyla kullanarak Windows 8 ve Windows Server 2012 web uygulamalardan verileri toplama [VSPerfASPNetCmd](../profiling/vsperfaspnetcmd.md).  
  
-   VsPerfCmd.exe kullanarak örnekleme verileri toplama.  
  
-   Örnekleme olay ve zamanlama aralığı ayarını veya ek performans sayacı verilerini toplama gibi örnekleme Seçenekleri'ni kullanın.  
  
##  <a name="BKMK_Collecting_tier_interaction__TIP__data"></a>Katman etkileşim (TIP) verileri toplama  
 Katman etkileşim profil veritabanları ADO.NET Hizmetleri aracılığıyla iletişim çok katmanlı uygulamaların işlevlerini yürütme sürelerinin hakkında ek bilgi sağlar. Verileri yalnızca zaman uyumlu işlev çağrıları için toplanır.  
  
 **Visual Studio sürümleri**  
  
 Katman etkileşimli profil oluşturma verilerini kullanarak toplanmasını [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], veya [!INCLUDE[vs_pro_current_short](../profiling/includes/vs_pro_current_short_md.md)]. Ancak, katman etkileşimli profil oluşturma verilerini yalnızca görüntülenebilir [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)] ve [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)].  
  
 **Windows 8 ve Windows Server 2012**  
  
1.  Windows 8 Masaüstü veya Windows Server 2012'de çalışan uygulamalardan katman etkileşim verileri toplamak için izleme metodunu kullanmanız gerekir.  
  
2.  UWP uygulamalar için katman etkileşim verileri toplayamazsınız.  
  
3.  Desteklenen diğer Windows sürümünde tüm profil oluşturma yöntemlerini katman etkileşim verileri içerebilir.  
  
 **Performans Sihirbazı'nı ve performans Gezgini**  
  
 Performans Gezgini'nden katman etkileşim verileri toplama seçeneğini profil çalışmaya eklemeniz gerekir. Proje, yürütülebilir dosya veya Web sitesi performans Gezgini hedef düğüme eklemelisiniz. Bkz: [katman etkileşim verileri toplama](../profiling/collecting-tier-interaction-data.md).  
  
 **Uzak makinede ipucu verileri toplama**  
  
 Uzak makinede katman etkileşim verileri toplamak için kopyalamanız gerekir **vs_profiler_***\<Platform >***_**  *\< Dil >***.exe** dosya *VSInstallDir %***\Team Tools\Performance Tools\Setups** bir Visual Studio makineyi klasörü Uzak bilgisayara yükleyin. Profil oluşturma araçları kullanamazsınız [uzaktan hata ayıklama](../debugger/remote-debugging.md) paketini indirin.  
  
 Kullanabileceğiniz [VSPerfCmd](../profiling/vsperfcmd.md) veya [VSPerfASPNetCmd](../profiling/vsperfaspnetcmd.md) profil oluşturma verileri toplamak için.  
  
 **İpucu raporları**  
  
 Katman etkileşim verileri yalnızca görüntülenebilir içinde [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)] veya [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)] IDE. Dosya tabanlı katman etkileşimli raporlar aracılığıyla [VSPerfReport](../profiling/vsperfreport.md) kullanılabilir değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans Gezgini](../profiling/performance-explorer.md)   
 [Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)   
 [Komut satırından profil oluşturma](../profiling/using-the-profiling-tools-from-the-command-line.md)