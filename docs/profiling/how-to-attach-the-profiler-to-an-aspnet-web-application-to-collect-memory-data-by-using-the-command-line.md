---
title: 'Nasıl yapılır: komut satırını kullanarak bellek verileri toplamak için bir ASP.NET Web uygulamasına profil oluşturucu ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: d608f85a-41ae-4ca7-85e6-b96624dbc83c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 0cd63358182c1e2e529bad02f372a6db8891652b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-memory-data-by-using-the-command-line"></a>Nasıl yapılır: Profil Oluşturucu Komut Satırını Kullanarak Bellek Verileri Toplamak için bir ASP.NET Web Uygulamasına Profil Oluşturucu Ekleme
Bu konuda nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] için profil oluşturucu ekleme için profil oluşturma araçları komut satırı araçları bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması ve toplama verileri sayısını ve boyutunu .NET Framework bellek ayırma hakkında. .NET Framework bellek nesnelerin ömrü hakkındaki verileri de toplayabilir.  
  
> [!NOTE]
>  Profil oluşturma araçları komut satırı araçları \Team Tools\Performance araçları alt dizininde bulunan [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64-bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Performans verileri toplamak için bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması kullanmalıdır [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) barındıran bilgisayarda uygun ortam değişkenlerini başlatmak için araç [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması. Ardından profil oluşturma için Web sunucusunu yapılandırmak için bilgisayarı yeniden başlatmanız gerekir.  
  
 Daha sonra [VSPerfCmd.exe](../profiling/vsperfcmd.md) için profil oluşturucu ekleme aracı [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web sitenizi barındıran çalışan işlemi. Uygulamaya profil oluşturucu eklendiğinde, duraklatma ve sürdürme veri toplama.  
  
 Profil oluşturma oturumu sona erdirmek için profil oluşturucu artık uygulamaya bağlı olması gerekir ve profil oluşturucu açıkça kapatılmalıdır. Çoğu durumda, bir oturumun sonunda profil ortam değişkenleri temizleme öneririz.  
  
## <a name="attaching-the-profiler"></a>Profil Oluşturucu ekleme  
  
#### <a name="to-attach-the-profiler-to-an-aspnet-web-application"></a>Bir ASP.NET Web uygulamasına profil oluşturucu eklemek için  
  
1.  Bir komut istemi penceresi açın.  
  
2.  Profil oluşturma ortam değişkenleri başlatır. Tür:  
  
     **VSPerfClrEnv** {**/globalsamplegc** &#124; **/globalsamplegclife**} [**/samplelineoff**]  
  
    -   Seçenekleri **/globalsamplegc** ve **/globalsamplegclife** bellek verileri toplamak için türünü belirtin.  
  
         Aşağıdaki seçeneklerden bir ve yalnızca bir tanesini belirtin.  
  
        |Seçenek|Açıklama|  
        |------------|-----------------|  
        |**/globalsamplegc**|Bellek ayırma verilerinin toplanmasını etkinleştirir.|  
        |**/globalsamplegclife**|Bellek ayırma verilerinin ve nesne yaşam süresi verilerinin toplanmasını etkinleştirir.|  
  
    -   Seçenek **/samplelineoff** belirli bir kaynak kod satırı için toplanan verileri atama devre dışı bırakır. Bu seçenek belirtilmişse, veri işlev düzeyinde atanır.  
  
3.  Yeni ortam yapılandırmasını ayarlamak için bilgisayarı yeniden başlatın.  
  
4.  Bir komut istemi penceresi açın. Gerekirse, profil yolu çevre değişken ayarlayın.  
  
5.  Profil Oluşturucu başlatın. Tür:  
  
     **VSPerfCmd**[/start](../profiling/start.md) **: örnek**[/çıkış](../profiling/output.md) **:** `OutputFile` [`Options`]      
  
    -   **/Start:sample** seçeneği profil oluşturucu başlatır.  
  
    -   **/Çıktı:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile` Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     İle aşağıdaki seçeneklerden birini kullanabilirsiniz **/start:sample** seçeneği.  
  
    > [!NOTE]
    >  **/User** ve **/crosssession** seçenekleri ASP.NET uygulamaları için genellikle gerekli.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|ASP.NET çalışan işlemin sahibi olan hesabın etki alanı ve kullanıcı adını belirtir. İşlem oturum açan kullanıcının başka bir kullanıcı olarak çalışıyorsa, bu seçeneği gereklidir. İşlem sahibi, Windows Görev Yöneticisi'nin İşlemler sekmesinde kullanıcı adı sütununda listelenir.|  
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturum açma oturumları işlemleri profil oluşturma. ASP.NET uygulamasını farklı bir oturumda çalışıyorsa, bu seçeneği gereklidir. Oturum tanımlayıcısı İşlemler sekmesinde Windows Görev Yöneticisi'nin oturum kimliği sütununda listelenir. **/CS** için bir kısaltma olarak belirtilen **/crosssession**.|  
    |[/waitstart](../profiling/waitstart.md) [**:**`Interval`]|Bir hata döndürmeden önce başlatmak profil oluşturucu için beklenecek saniye sayısını belirtir. Varsa `Interval` belirtilmezse, profil oluşturucu sonsuza kadar bekler. Varsayılan olarak, **/start** hemen döndürür.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|  
  
6.  Başlat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması normal şekilde.  
  
7.  Profil Oluşturucu ekleme [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] çalışan işlemi. Tür:  
  
     **VSPerfCmd**[/ attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [[/targetclr](../profiling/targetclr.md)**:**`Version`]    
  
    -   İşlem Kimliği `(PID)` işlem kimliği veya işlem adını belirtir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] çalışan işlemi. İşlem tüm çalışan işlemleri kimliklerini Windows Görev Yöneticisi'nde görüntüleyebilirsiniz.  
  
    -   **/targetclr:** `Version` bir uygulamada birden fazla çalışma zamanı sürümü yüklendiğinde profiline ortak dil çalışma zamanı (CLR) sürümünü belirtir.  
  
## <a name="controlling-data-collection"></a>Veri Toplama Denetimi  
 Uygulama çalışırken, başlatma ve kullanarak profil oluşturucu veri dosyası için veri yazma durdurma tarafından veri toplama denetleyebilirsiniz **VSPerfCmd.exe** seçenekleri. Veri toplama denetimi, program yürütme, başlatılıyor veya uygulama kapatılmadan gibi belirli bir bölümü için veri toplamanıza olanak sağlar.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Aşağıdaki çiftleri **VSPerfCmd** seçenekleri başlatma ve durdurma veri toplama. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) tarafından belirtilen işlem için veri toplama `PID`.|  
    |**/ ekleme:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;:`ProcName`}]|**/ attach** işlem kimliği veya işlem adı tarafından belirtilen işlem için veri toplamaya başlar. **/ detach** belirli bir işlemin belirtilmezse, tüm işlemler veya belirtilen işlem için veri toplamayı durdurur.|  
  
## <a name="ending-the-profiling-session"></a>Profil oluşturma oturumu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için Profil Oluşturucu Web uygulamasından ayrılmış olması gerekir. Örnekleme yöntemi ile başlatarak profili bir uygulama veri toplamayı Durdur [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] çalışan işlem veya çağırarak **VSPerfCmd / detach** seçeneği. Ardından çağıran **VSPerfCmd** [shutdown](../profiling/shutdown.md) profil oluşturucu devre dışı bırakma ve profil oluşturma veri dosyası kapatmak için seçeneği. **VSPerfClrEnv /globaloff** komutu temizler profil ortam değişkenleri, ancak bilgisayar yeniden başlatılana kadar sistem yapılandırması sıfırlanmaz.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Profil Oluşturucu hedef uygulamasından ayırmak için aşağıdaki adımlardan birini gerçekleştirin:  
  
    -   Tür **VSPerfCmd** [/ Ayır](../profiling/detach.md)  
  
         -veya-  
  
    -   Kapat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] çalışan işlemi. Tür:  
  
     **IISReset/stop**  
  
2.  Profil Oluşturucu kapatın. Tür:  
  
     **VSPerfCmd Shutdown**  
  
3.  (İsteğe bağlı) Profil oluşturma ortam değişkenleri temizleyin. Tür:  
  
     **VSPerfCmd /globaloff**  
  
4.  Bilgisayarı yeniden başlatın. Gerekirse, Internet Information Services (IIS) yeniden başlatın. Tür:  
  
     **IISReset/Start**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [.NET bellek verisi görünümleri](../profiling/dotnet-memory-data-views.md)