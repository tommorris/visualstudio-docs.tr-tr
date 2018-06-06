---
title: 'Nasıl yapılır: Profil oluşturucu komut satırını kullanarak dinamik olarak derlenmiş ASP.NET web uygulamasını ve bellek verileri toplamak izleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 2cdd9903-39db-47e8-93dd-5e6a21bc3435
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 6ef538ac7316375b14dcbd951d5cf89702cdde0e
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815593"
---
# <a name="how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line"></a>Nasıl yapılır: dinamik olarak derlenmiş bir ASP.NET web uygulamasını izleme ve profil oluşturucu komut satırını kullanarak bellek verileri toplama
Bu konuda nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ayrıntılı .NET bellek ayırma ve nesne yaşam süresi verilerini dinamik olarak derlenmiş toplamak için profil oluşturma araçları komut satırı araçları [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] web uygulaması izleme profili oluşturma yöntemi kullanarak.  
  
> [!NOTE]
>  Profil oluşturma araçları komut satırı araçları içinde bulunur *\Team Tools\Performance Araçları* alt [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64-bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Performans verileri toplamak için bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] web uygulaması, değişiklik *web.config* etkinleştirmek için hedef uygulamanın dosya [VSInstr.exe](../profiling/vsinstr.md) dinamik olarak derlenmiş işaretlemesini aracı Uygulama dosyaları. Daha sonra [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) barındıran sunucuyu yapılandırmak için aracı [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması ve uygun ortam değişkenlerini ayarlayarak .NET bellek profili oluşturma etkinleştirin ve ardından bilgisayarı yeniden başlatın.  
  
 Verileri toplamak için profil oluşturucu başlatın ve ardından hedef uygulama çalıştırın. Profil Oluşturucu uygulamaya bağlı olsa da, duraklatma ve veri toplama sürdürme. Uygun verileri topladığınızda, uygulamayı kapatın, Internet Information Services (IIS) çalışan işlem kapatın ve ardından profil oluşturucuyu kapatın.  
  
 Profil oluşturma iş tamamlandığında geri *web.config* dosya ve özgün durumlarına web sunucusu.  
  
## <a name="configure-the-aspnet-web-application-and-the-web-server"></a>ASP.NET web uygulaması ve web sunucusu yapılandırma  
  
#### <a name="to-configure-the-aspnet-web-application-and-the-web-server"></a>ASP.NET web uygulaması ve web sunucusu yapılandırmak için  

1.  Değiştirme *web.config* hedef uygulamanın dosya. Bkz: [nasıl yapılır: izleme ve profil dinamik olarak derlenmiş ASP.NET web uygulamaları için web.config dosyalarını değiştirme](../profiling/how-to-modify-web-config-files-to-instrument-dynamically-compiled-aspnet-apps.md).  
  
2.  Web uygulamasını barındıran bilgisayarda bir komut istemi penceresi açın.  
  
3.  Profil oluşturma ortam değişkenleri başlatır. Tür:  
  
     **VSPerfClrEnv /globaltracegc**  
  
     veya  
  
     **VSPerfClrEnv /globaltracegclife**  
  
    -   **/globaltracegc** bellek ayırma verilerin toplanmasını sağlar.  
  
    -   **/globaltracegclife** bellek ayırma verileri ve nesne yaşam verisi koleksiyonunu sağlar.  
  
4.  Bilgisayarı yeniden başlatın.  
  
## <a name="run-the-profiling-session"></a>Profil oluşturma oturumu çalıştırın  
  
#### <a name="to-profile-the-aspnet-web-application"></a>Profil ASP.NET web uygulaması  
  
1.  Profil Oluşturucu başlatın. Tür:  
  
     **VSPerfCmd** [/start](../profiling/start.md) **: izleme** [/çıkış](../profiling/output.md) **:** `OutputFile` [`Options`]  
  
    -   **/Start:trace** seçeneği profil oluşturucu başlatır.  
  
    -   **/Çıktı:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile` Profil oluşturma verileri konumunu ve adını belirtir (. *Vsp*) dosyası.  
  
     İle aşağıdaki seçeneklerden birini kullanabilirsiniz **/start:trace** seçeneği.  
  
    > [!NOTE]
    >  **/User** ve **/crosssession** seçenekleri ASP.NET uygulamaları için genellikle gerekli.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Sahibi olan hesabın isteğe bağlı etki alanı ve kullanıcı adını belirtir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] çalışan işlemi. İşlem oturum açan kullanıcının başka bir kullanıcı olarak çalışıyorsa, bu seçeneği gereklidir. Ad içinde listelenir **kullanıcı adı** sütunu **işlemleri** sekmesi Windows Görev Yöneticisi'nin.|  
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturumlarda işlemleri profil oluşturma. Bu seçenek, uygulamanın farklı bir oturumda çalışıyorsa gereklidir. Oturum kimliği listelenir **oturum kimliği** sütunu **işlemleri** sekmesi Windows Görev Yöneticisi'nin. **/CS** için bir kısaltma olarak belirtilen **/crosssession**.|  
    |[/globaloff](../profiling/globalon-and-globaloff.md)|Profil Oluşturucu veri koleksiyonu duraklatıldı başlatır. Kullanım [/globalon](../profiling/globalon-and-globaloff.md) profil sürdürmek için.|  
    |[/ sayacı](../profiling/counter.md) **:** `Config`|Belirtilen sayaç işlemci performansı bilgi toplar `Config`. Sayaç bilgileri her profil olay, toplanan veriler eklenir.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı bir toplanır (. *etl*) dosyası.|  
  
2.  Başlat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] web uygulaması normal şekilde.  
  
## <a name="control-data-collection"></a>Veri toplamayı denetleme  
 Hedef uygulama çalışırken, başlatma ve kullanarak profil oluşturucu veri dosyası için veri yazma durdurma tarafından veri toplama denetleyebilirsiniz *VSPerfCmd.exe* seçenekleri. Veri toplama denetimi, program yürütme, başlatılıyor veya uygulama kapatılmadan gibi belirli bir bölümü için veri toplamanıza olanak sağlar.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Seçenekler aşağıdaki çiftleri başlatın ve veri toplama işlemini durdurun. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) işlem kimliği tarafından belirtilen işlem için veri toplama (`PID`).|  
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:** `TID`|Başlatır (**/threadon**) veya durdurulduğunda (**/threadoff**) Kimlikli iş parçacığı tarafından belirtilen iş parçacığı için veri toplama (`TID`).|  
  
-   Aynı zamanda **VSPerfCmd.exe**[/işaretlemek](../profiling/mark.md) profil işareti veri dosyasına eklemek için seçeneği. **/İşaretlemek** komut tanımlayıcı, bir zaman damgası ve bir kullanıcı tanımlı isteğe bağlı bir metin dizesi ekler. İşaretleri Profil Oluşturucusu rapor ve veri görünümleri verilerini filtrelemek için kullanılabilir.  
  
## <a name="end-the-profiling-session"></a>Profil oluşturma oturumunu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için hedef kapatmak [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] web uygulaması, profili işlemini durdurun ve sonra Profil Oluşturucu kapatmak için Internet Information Services (IIS) durdurun. Ardından IIS'yi yeniden başlatın.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Kapat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] web uygulaması.  
  
2.  Kapat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Internet Information Services (IIS) sıfırlama tarafından çalışan işlemi. Tür:  
  
     **IISReset/stop**  
  
3.  Profil Oluşturucu kapatın. Tür:  
  
     **VSPerfCmd** [Shutdown](../profiling/shutdown.md)  
  
4.  IIS'yi yeniden başlatın. Tür:  
  
     **IISReset/Start**  
  
## <a name="restore-the-application-and-computer-configuration"></a>Uygulama ve bilgisayar yapılandırmasını geri yükleme  
 Tüm profil oluşturmayı tamamladıktan sonra yerine *web.config* dosya, profil ortam değişkenleri temizleyin ve sunucuyu geri yüklemek için bilgisayarı yeniden başlatın ve [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] özgün durumlarına uygulama.  
  
#### <a name="to-restore-the-application-and-computer-configuration"></a>Uygulama ve bilgisayar yapılandırmasını geri yüklemek için  
  
1.  Değiştir *web.config* dosya özgün dosyanın bir kopyasını.  
  
2.  (İsteğe bağlı). Profil oluşturma ortam değişkenleri temizleyin. Tür:  
  
     **VSPerfCmd /globaloff**  
  
3.  Bilgisayarı yeniden başlatın.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Profil ASP.NET web uygulamaları](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [.NET bellek verisi görünümleri](../profiling/dotnet-memory-data-views.md)
