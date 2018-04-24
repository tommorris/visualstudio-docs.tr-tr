---
title: 'Nasıl yapılır: komut satırını kullanarak uygulama istatistikleri toplamak için bir ASP.NET Web uygulamasına profil oluşturucu ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 3725ddbe-ce91-4469-991e-8c5ed048c618
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: a916e1d3410957a3f03c82436dee6f84bd57726b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-application-statistics-by-using-the-command-line"></a>Nasıl yapılır: Komut Satırını Kullanarak Uygulama İstatistikleri Verileri Toplamak için bir ASP.NET Web Uygulamasına Profil Oluşturucu Ekleme
Bu konuda nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir ASP.NET Web uygulamasına profil oluşturucu ekleme ve örnekleme yöntemini kullanarak performans istatistikleri toplamak için profil oluşturma araçları komut satırı araçları.  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
>   
>  Profil oluşturma çalışmaya katman etkileşim verileri ekleme belirli yordamları profil oluşturma araçları komut satırıyla gerektirir. Bkz: [katman etkileşim verileri toplama](../profiling/adding-tier-interaction-data-from-the-command-line.md).  
>   
>  Profil oluşturma araçları komut satırı araçları \Team Tools\Performance araçları alt dizininde bulunan [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64-bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Bir ASP.NET Web uygulamasından performans verilerini toplamak için uygun ortam değişkenlerini başlatılmalıdır ve profil oluşturma için Web sunucusunu yapılandırmak için ASP.NET Web uygulamasını barındıran bilgisayarın yeniden başlatılması.  
  
 Ardından, Web sitenizi barındıran ASP.NET çalışan işlemi için profil oluşturucu ekleme. Uygulamaya profil oluşturucu eklendiğinde, duraklatma ve sürdürme veri toplama.  
  
 Profil oluşturma oturumu sona erdirmek için profil oluşturucu profili uygulamadan ayrılmış olmalıdır ve profil oluşturucu açıkça kapatılmalıdır. Çoğu durumda, bir oturumun sonunda profil ortam değişkenleri temizleme öneririz.  
  
## <a name="starting-the-profiler-and-attaching-to-an-aspnet-web-application"></a>Profil oluşturucu başlatma ve bir ASP.NET Web uygulamasına ekleniyor  
  
#### <a name="to-attach-the-profiler-to-an-aspnet-web-application"></a>Bir ASP.NET Web uygulamasına profil oluşturucu eklemek için  
  
1.  Bir komut istemi penceresi açın.  
  
2.  Profil oluşturma ortam değişkenleri başlatır. Tür:  
  
     **VSPerfClrEnv /globalsampleon** [**/samplelineoff**]  
  
    -   **/globalsampleon** örnekleme sağlar.  
  
    -   **/samplelineoff** belirli bir kaynak kod satırı için toplanan verileri atama devre dışı bırakır. Bu seçenek belirtildiğinde, verileri yalnızca işlevleriyle atanır.  
  
3.  Bilgisayarı yeniden başlatın.  
  
4.  Profil Oluşturucu başlatın. Tür:**VSPerfCmd** [/start](../profiling/start.md)**: örnek** [/çıkış](../profiling/output.md)**:**`OutputFile`[`Options`]  
  
    -   **/Start:sample** seçeneği profil oluşturucu başlatır.  
  
    -   **/Çıktı:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile` Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     Aşağıdaki seçenekler herhangi birini kullanabilirsiniz **/start:sample** seçeneği.  
  
    > [!NOTE]
    >  **/User** ve **/crosssession** seçenekleri ASP.NET uygulamaları için genellikle gerekli.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|ASP.NET çalışan işlemin sahibi olan hesabın etki alanı ve kullanıcı adını belirtir. İşlem oturum açan kullanıcının başka bir kullanıcı olarak çalışıyorsa, bu seçeneği gereklidir. İşlem sahibi, Windows Görev Yöneticisi'nin İşlemler sekmesinde kullanıcı adı sütununda listelenir.|  
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturum açma oturumları işlemleri profil oluşturma. ASP.NET uygulamasını farklı bir oturumda çalışıyorsa, bu seçeneği gereklidir. Oturum tanımlayıcısı İşlemler sekmesinde Windows Görev Yöneticisi'nin oturum kimliği sütununda listelenir. **/CS** için bir kısaltma olarak belirtilen **/crosssession**.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|  
  
5.  ASP.NET Web uygulaması normal şekilde başlatın.  
  
6.  Profil Oluşturucu ASP.NET çalışan işleme iliştirilemiyor. Tür:**VSPerfCmd** [/ attach](../profiling/attach.md)**:**{`PID`&#124;`ProcName`} [`Sample Event`] [[/targetclr](../profiling/targetclr.md) **:**`Version`]  
  
    -   `PID` ASP.NET çalışan işlemin işlem kimliği belirtir; `ProcName` çalışan işlem adını belirtir. Windows Görev Yöneticisi'nde işlem kimlikleri ve adları tüm çalışan işlemleri görüntüleyebilirsiniz.  
  
    -   Varsayılan olarak, performans verileri her 10,000,000 durdurulamaz harici işlemci saatinin örneklenen döngüleri. Yaklaşık 100 kez 1GH işlemci saniye başına budur. Aşağıdakilerden birini belirtebilirsiniz **VSPerfCmd** saat döngüsü aralığını değiştirmek için ya da farklı örnekleme olay belirtmek için Seçenekler.  
  
    |Örnek olayı|Açıklama|  
    |------------------|-----------------|  
    |[/Timer](../profiling/timer.md) **:** `Interval`|Örnekleme aralığı tarafından belirtilen durdurulamaz harici saat döngüsü sayısını değiştirir `Interval`.|  
    |[/PF](../profiling/pf.md)[**:**`Interval`]|Örnekleme olay sayfa hataları değiştirir. Varsa `Interval` belirtilmemişse, örnekler arasındaki sayfa hatalarının sayısını ayarlar. Varsayılan 10'dur.|  
    |[/ sys](../profiling/sys-vsperfcmd.md)[`:``Interval`]|Örnekleme olay sistem çağrıları (syscalls) işletim sistemi çekirdeğe işleminden değiştirir. Varsa `Interval` belirtilmemişse, örnekler arasındaki çağrılarının sayısını ayarlar. Varsayılan 10'dur.|  
    |[/ sayacı](../profiling/counter.md) **:** `Config`|Belirtilen aralığı ve işlemci performans sayacı örnekleme olay ve aralığı değişikliklerini `Config`.|  
    |[/targetclr](../profiling/targetclr.md) **:** `Version`|Ortak dil çalışma zamanı (CLR) bir uygulamada birden fazla çalışma zamanı sürümü yüklendiğinde profilini sürümünü belirtir.|  
  
    -   **targetclr:** `Version` bir uygulamada birden fazla çalışma zamanı sürümü yüklendiğinde profiline CLR sürümünü belirtir. İsteğe bağlı.  
  
## <a name="controlling-data-collection"></a>Veri Toplama Denetimi  
 Uygulama çalışırken, başlatma ve kullanarak verileri dosyaya yazma durdurma tarafından veri toplama denetleyebilirsiniz **VSPerfCmd.exe** seçenekleri. Veri toplama denetimi, program yürütme, başlatılıyor veya uygulama kapatılmadan gibi belirli bir bölümü için veri toplamanıza olanak sağlar.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Aşağıdaki çiftleri **VSPerfCmd** seçenekleri başlatma ve durdurma veri toplama. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` **/processoff:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) tarafından belirtilen işlem için veri toplama `PID`.|  
    |[/ attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ attach** tarafından belirtilen işlem için veri toplamaya başlar `PID` veya işlem adı (ProcName). **/ detach** belirli bir işlemin belirtilmezse, tüm işlemler veya belirtilen işlem için veri toplamayı durdurur.|  
  
## <a name="ending-the-profiling-session"></a>Profil oluşturma oturumu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için kapatmak [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması ve Internet Information Services (IIS) kullanan **IISReset** kapatmak için komut [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] çalışan işlemi. Çağrı **VSPerfCmd** [shutdown](../profiling/shutdown.md) profil oluşturucu devre dışı bırakma ve profil oluşturma veri dosyası kapatmak için seçeneği.  
  
 **VSPerfClrEnv /globaloff** komutu profil ortam değişkenleri temizler. Yeni ortam ayarlarının uygulanması için bilgisayarı yeniden başlatmanız gerekir.  
  
 **VSPerfClrEnv /globaloff** komutu temizler profil ortam değişkenleri, ancak bilgisayar yeniden başlatılana kadar sistem yapılandırması sıfırlanmaz.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Profil Oluşturucu hedef uygulamasından ayırmak için aşağıdakilerden birini yapın:  
  
    -   Tür **VSPerfCmd / Ayır**  
  
         -veya-  
  
    -   Kapat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] çalışan işlemi.  
  
2.  Profil Oluşturucu kapatın. Tür:**VSPerfCmd** [Shutdown](../profiling/shutdown.md)  
  
3.  (İsteğe bağlı) Profil oluşturma ortam değişkenleri temizleyin. Tür:  
  
     **VSPerfCmd /globaloff**  
  
4.  Bilgisayarı yeniden başlatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Örnekleme yöntemi veri görünümleri](../profiling/profiler-sampling-method-data-views.md)