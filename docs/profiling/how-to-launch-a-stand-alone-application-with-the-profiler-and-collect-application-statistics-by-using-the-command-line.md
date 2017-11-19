---
title: "Nasıl yapılır: komut satırını kullanarak uygulama istatistikleri toplama ve Profil Oluşturucu ile bağımsız bir uygulama başlatma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52dcee2b-f178-4a76-bddc-e36c50bfcb78
caps.latest.revision: "37"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 17a5d01ed0ceb139362c28168d430f19ea0fef55
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="how-to-launch-a-stand-alone-application-with-the-profiler-and-collect-application-statistics-by-using-the-command-line"></a>Nasıl yapılır: Profil Oluşturucu ile Bağımsız bir Uygulama Başlatma ve Komut Satırını Kullanarak Uygulama İstatistikleri Toplama
Bu konuda nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir tek başına (istemci) uygulamasını başlatıp örnekleme yöntemini kullanarak performans istatistikleri toplamak için profil oluşturma araçları komut satırı araçları.  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
>   
>  Profil oluşturma çalışmaya katman etkileşim verileri ekleme belirli yordamları profil oluşturma araçları komut satırıyla gerektirir. Bkz: [katman etkileşim verileri toplama](../profiling/adding-tier-interaction-data-from-the-command-line.md)  
  
 Profil oluşturucu komut satırı araçları kullanmak için komut istemi penceresini PATH ortam değişkenine yolu ekleyin veya komutuna ekleyin. Profil Araçları Visual Studio bir Visual Studio komut penceresinde yüklendiği bir makinede çalıştırabilirsiniz.  
  
1.  Visual Studio olduğu bir makineye profil oluşturma araçları çalıştıran bir Visual Studio komut penceresinde kümelerini doğru yolları yüklü. Üzerinde **Araçları** menüsünde seçin **VS komut istemi**  
  
> [!NOTE]
>  Profil Oluşturma Araçlarının komut satırı araçları, Visual Studio yükleme dizini altındaki \Team Tools\Performance Tools alt dizininde yer alır. 64-bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçları kullanmak için komut istemi penceresini PATH ortam değişkenine yolu ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
## <a name="starting-the-application-with-the-profiler"></a>Profil Oluşturucu ile uygulama başlatma  
 Profil Oluşturucu kullanarak bir hedef uygulama başlatmak için VSPerfCmd kullanın **/start** ve **/başlatma** profil oluşturucu başlatın ve uygulamayı başlatmak için Seçenekler. Belirleyebileceğiniz **/start** ve **/başlatma** ve bunların ilgili tek bir komut satırı seçenekleri.  
  
 Ayrıca ekleyebileceğiniz **/globaloff** hedef uygulama başlangıcında veri toplamayı duraklatmak için seçeneği. Daha sonra **/globalon** veri toplamaya başlamak için.  
  
#### <a name="to-start-an-application-by-using-the-profiler"></a>Profil Oluşturucu kullanarak bir uygulamayı başlatmak için  
  
1.  Bir komut istemi penceresi açın.  
  
2.  Profil Oluşturucu başlatın. Tür:  
  
     **VSPerfCmd /start:sample/Output:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md)**: örnek** seçeneği profil oluşturucu başlatır.  
  
    -   [/Çıkış](../profiling/output.md)**:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile`Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     İle aşağıdaki seçeneklerden birini kullanabilirsiniz **/start:sample** seçeneği.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/wincounter](../profiling/wincounter.md) **:**`WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:**`Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:**`Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|  
  
3.  Hedef uygulama başlatın. Tür:**VSPerfCmd /launch:** `appName` [`Options`] [`Sample Event`]  
  
     Bir veya daha fazla ile aşağıdaki seçenekleri kullanabilirsiniz **/başlatma** seçeneği.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/args](../profiling/args.md) **:**`Arguments`|Hedef uygulamaya geçirilecek komut satırı bağımsız değişkenleri içeren bir dize belirtir.|  
    |[/ Console](../profiling/console.md)|Hedef komut satırı uygulaması ayrı bir pencerede başlatır.|  
  
     Varsayılan olarak, performans verileri her 10,000,000 durdurulamaz harici işlemci saatinin örneklenen döngüleri. Yaklaşık bir saat 10 saniyede bir 1 GHz işlemci üzerinde budur. Saat döngüsü aralığını değiştirmek için ya da farklı örnekleme olay belirtmek için aşağıdaki seçeneklerden birini belirtebilirsiniz.  
  
    |Örnek olayı|Açıklama|  
    |------------------|-----------------|  
    |[/Timer](../profiling/timer.md) **:**`Interval`|Örnekleme aralığı tarafından belirtilen durdurulamaz harici saat döngüsü sayısını değiştirir `Interval`.|  
    |[/PF](../profiling/pf.md)[**:**`Interval`]|Örnekleme olay sayfa hataları değiştirir. Varsa `Interval` belirtilmemişse, örnekler arasındaki sayfa hatalarının sayısını ayarlar. Varsayılan 10'dur.|  
    |[/ sys](../profiling/sys-vsperfcmd.md)[**:**`Interval`]|Örnekleme olay sistem çağrıları (syscalls) işletim sistemi çekirdeğe işleminden değiştirir. Varsa `Interval` belirtilmemişse, örnekler arasındaki çağrılarının sayısını ayarlar. Varsayılan 10'dur.|  
    |[/ sayacı](../profiling/counter.md) **:**`Config`|Belirtilen aralığı ve işlemci performans sayacı örnekleme olay ve aralığı değişikliklerini `Config`.|  
  
## <a name="controlling-data-collection"></a>Veri Toplama Denetimi  
 Hedef uygulama çalışırken, başlatma ve kullanarak profil oluşturucu veri dosyası için veri yazma durdurma tarafından veri toplama denetleyebilirsiniz **VSPerfCmd.exe** seçenekleri. Veri toplama denetimi, program yürütme, başlatılıyor veya uygulama kapatılmadan gibi belirli bir bölümü için veri toplamanıza olanak sağlar.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Seçenekler aşağıdaki çiftleri başlatın ve veri toplama işlemini durdurun. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:**  `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) işlem kimliği tarafından belirtilen işlem için veri toplama (`PID`).|  
    |[/ attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ attach** tarafından belirtilen işlem için veri toplamaya başlar `PID` veya işlem adı (ProcName). **/ detach** belirli bir işlemin belirtilmezse, tüm işlemler veya belirtilen işlem için veri toplamayı durdurur.|  
  
## <a name="ending-the-profiling-session"></a>Profil oluşturma oturumu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için profil oluşturucu herhangi bir profili işlem bağlanamaz ve profil oluşturucu açıkça kapatılmalıdır. Profil Oluşturucu uygulamadan uygulama kapatarak veya çağırarak örnekleme yöntemini kullanarak profili ayırabilirsiniz **VSPerfCmd / detach** seçeneği. Ardından çağıran **VSPerfCmd shutdown** profil oluşturucu kapatmak ve profil oluşturma veri dosyası kapatmak için seçeneği. **VSPerfClrEnv / kapalı** komutu profil ortam değişkenleri temizler.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Profil Oluşturucu hedef uygulamasından ayırmak için aşağıdaki adımlardan birini gerçekleştirin:  
  
    -   Hedef uygulamayı kapatın.  
  
         veya  
  
    -   Tür **VSPerfCmd / Ayır**  
  
2.  Profil Oluşturucu kapatın. Tür:  
  
     **VSPerfCmd**[Shutdown  ](../profiling/shutdown.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Örnekleme yöntemi veri görünümleri](../profiling/profiler-sampling-method-data-views.md)