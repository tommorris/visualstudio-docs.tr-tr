---
title: 'Nasıl yapılır: profil oluşturucuyu bir .NET Framework bağımsız uygulamasına ekleme ve komut satırını kullanarak uygulama istatistikleri toplama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: b62fcbc1-791f-474e-890a-a6c332e0c9ea
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: c51b981e7863db371d8e50ae13e48afbc7f270fc
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="how-to-attach-the-profiler-to-a-net-framework-stand-alone-application-and-collect-application-statistics-by-using-the-command-line"></a>Nasıl yapılır: profil oluşturucuyu bir .NET Framework bağımsız uygulamasına ekleme ve komut satırını kullanarak uygulama istatistikleri toplama
Bu konuda nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çalışan bir .NET Framework tek başına (istemci) uygulamaya profil oluşturucu ekleme ve örnekleme yöntemini kullanarak performans istatistikleri toplamak için profil oluşturma araçları komut satırı araçları.  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
>   
>  Profil oluşturma araçları komut satırı araçları \Team Tools\Performance araçları alt dizininde bulunan [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64-bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
>   
>  Profil oluşturma çalışmaya katman etkileşim verileri ekleme belirli yordamları profil oluşturma araçları komut satırıyla gerektirir. Bkz: [katman etkileşim verileri toplama](../profiling/adding-tier-interaction-data-from-the-command-line.md).  
  
 Hedef Uygulama başlatılmadan önce bir .NET Framework uygulamasından performans verilerini toplamak için uygun ortam değişkenlerini başlatılması gerekir. Uygulamaya profil oluşturucu eklendiğinde, duraklatma ve sürdürme veri toplama.  
  
 Profil oluşturma oturumu sona erdirmek için profil oluşturucu artık uygulamaya bağlı olması gerekir ve profil oluşturucu açıkça kapatılmalıdır. Çoğu durumda, bir profil oluşturma oturumu sonunda profil ortam değişkenleri temizleme öneririz.  
  
## <a name="attach-the-profiler"></a>Profil Oluşturucu ekleme  
  
#### <a name="to-attach-the-profiler-to-a-running-net-framework-application"></a>Profil Oluşturucu çalışan bir .NET Framework uygulama eklemek için  
  
1.  Bir komut istemi penceresi açın.  
  
2.  Profil oluşturma ortam değişkenleri başlatır. Tür:  
  
     **VSPerfClrEnv /sampleon** [**/samplelineoff**]  
  
    -   **/Samplelineoff** seçeneği, kaynak kodu satır numarası veri koleksiyonunu devre dışı bırakır.  
  
3.  Profil Oluşturucu başlatın. Tür:  
  
     **VSPerfCmd /start:sample/Output:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md)**: örnek** seçeneği profil oluşturucu başlatır.  
  
    -   [/Çıkış](../profiling/output.md)**:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile` Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     Aşağıdaki seçenekler herhangi birini kullanabilirsiniz **/start:sample** seçeneği.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|İsteğe bağlı etki alanı ve kullanıcı profili işlem sahip hesabın adını belirtir. Bu seçenek, yalnızca profili uygulamanın oturum açan kullanıcının başka bir kullanıcı olarak başlatıldıysa gereklidir.|  
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturum açma oturumları işlemleri profil oluşturma. **/CS** için bir kısaltma olarak belirtilen **/crosssession**. Bu seçenek, uygulamanın farklı bir oturumda çalışıyorsa gereklidir.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|  
  
4.  Gerekirse, hedef uygulamanın normal şekilde başlatın.  
  
5.  Hedef uygulama için profil oluşturucu ekleme. Tür:  
  
     **VSPerfCmd / ekleme:**{`PID`&#124;`ProcessName`} [`Sample Event`] [**/targetclr:**`Version`]  
  
    -   `PID` Hedef uygulama işlem Kimliğini belirtir. `ProcessName` işlemin adını belirtir. Belirttiğiniz gerçekleştiriyorsanız `ProcessName` ve aynı ada sahip birden çok işlem çalıştırıyorsanız, sonuçlar tahmin edilemez. İşlem tüm çalışan işlemleri kimliklerini Windows Görev Yöneticisi'nde görüntüleyebilirsiniz.  
  
    -   [/targetclr](../profiling/targetclr.md) **:** `Version` bir uygulamada birden fazla çalışma zamanı sürümü yüklendiğinde profiline ortak dil çalışma zamanı (CLR) sürümünü belirtir. İsteğe bağlı.  
  
    -   Varsayılan olarak, performans verileri her 10,000,000 durdurulamaz harici işlemci saatinin örneklenen döngüleri. Yaklaşık bir saat 10 saniyede 1GH işlemcide budur. Saat döngüsü aralığını değiştirmek için ya da farklı örnekleme olay belirtmek için aşağıdaki seçeneklerden birini belirtebilirsiniz. [/targetclr](../profiling/targetclr.md)**:** `Version` bir uygulamada birden fazla çalışma zamanı sürümü yüklendiğinde profiline CLR sürümünü belirtir. İsteğe bağlı.  
  
    |||  
    |-|-|  
    |Örnek olayı|Açıklama|  
    |[/Timer](../profiling/timer.md) **:** `Interval`|Örnekleme aralığı tarafından belirtilen durdurulamaz harici saat döngüsü sayısını değiştirir `Interval`.|  
    |[/PF](../profiling/pf.md) [**:**`Interval`]|Örnekleme olay sayfa hataları değiştirir. Varsa `Interval` belirtilmemişse, örnekler arasındaki sayfa hatalarının sayısını ayarlar. Varsayılan 10'dur.|  
    |[/ sys](../profiling/sys-vsperfcmd.md) [**:**`Interval`]|Örnekleme olay sistem çağrıları (syscalls) işletim sistemi çekirdeğe işleminden değiştirir. Varsa `Interval` belirtilmemişse, örnekler arasındaki çağrılarının sayısını ayarlar. Varsayılan 10'dur.|  
    |[/ sayacı](../profiling/counter.md) **:** `Config`|Belirtilen aralığı ve işlemci performans sayacı örnekleme olay ve aralığı değişikliklerini `Config`.|  
  
     
  
## <a name="control-data-collection"></a>Denetimin veri toplama  
 Hedef uygulama çalışırken, başlatma ve kullanarak profil oluşturucu veri dosyası için veri yazma durdurma tarafından veri toplama denetleyebilirsiniz **VSPerfCmd.exe** seçenekleri. Veri toplama denetimi, program yürütme, başlatılıyor veya uygulama kapatılmadan gibi belirli bir bölümü için veri toplamanıza olanak sağlar.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Seçenekler aşağıdaki çiftleri başlatın ve veri toplama işlemini durdurun. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) tarafından belirtilen işlem için veri toplama `PID`.|  
    |[/ attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ attach** tarafından belirtilen işlem için veri toplamaya başlar `PID` veya işlem adı (ProcName). **/ detach** belirli bir işlemin belirtilmezse, tüm işlemler veya belirtilen işlem için veri toplamayı durdurur.|  
  
## <a name="end-the-profiling-session"></a>Profil oluşturma oturumunu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için profil oluşturucu tüm profili işlemlerini ayrılmış olmalıdır ve profil oluşturucu açıkça kapatılmalıdır. Profil Oluşturucu uygulamadan uygulama kapatarak veya çağırarak örnekleme yöntemini kullanarak profili ayırabilirsiniz **VSPerfCmd / detach** seçeneği. Ardından çağıran **VSPerfCmd shutdown** profil oluşturucu kapatmak ve profil oluşturma veri dosyası kapatmak için seçeneği. **VSPerfClrEnv / kapalı** komutu profil ortam değişkenleri temizler.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Profil Oluşturucu hedef uygulamasından ayırmak için aşağıdaki adımlardan birini gerçekleştirin:  
  
    -   Tür **VSPerfCmd / Ayır**  
  
         -veya-  
  
    -   Hedef uygulamayı kapatın.  
  
2.  Profil Oluşturucu kapatın. Tür:  
  
     **VSPerfCmd**[Shutdown](../profiling/shutdown.md)  
  
3.  (İsteğe bağlı) Profil oluşturma ortam değişkenleri temizleyin. Tür:  
  
     **VSPerfClrEnv / kapalı**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Örnekleme yöntemi veri görünümleri](../profiling/profiler-sampling-method-data-views.md)