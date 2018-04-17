---
title: 'Nasıl yapılır: dinamik olarak derlenmiş bir ASP.NET Web uygulamasını izleme profil oluşturucu komut satırını kullanarak uygulama ve bellek verileri toplama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 2cdd9903-39db-47e8-93dd-5e6a21bc3435
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 47a2bbe572b153cdddc6d0108b912f8a98e64c07
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line"></a>Nasıl yapılır: Profil Oluşturucu Komut Satırını Kullanarak Dinamik Olarak Derlenmiş bir ASP.NET Web Uygulamasını İzleme ve Bellek Verileri Toplama
Bu konuda nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ayrıntılı .NET bellek ayırma ve nesne yaşam süresi verilerini dinamik olarak derlenmiş toplamak için profil oluşturma araçları komut satırı araçları [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması izleme profili oluşturma yöntemi kullanarak.  
  
> [!NOTE]
>  Profil oluşturma araçları komut satırı araçları \Team Tools\Performance araçları alt dizininde bulunan [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64 bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Performans verileri toplamak için bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulamasını etkinleştirmek için hedef uygulamanın web.config dosyasında değişiklik [VSInstr.exe](../profiling/vsinstr.md) dinamik olarak derlenmiş uygulama dosyaları işaretleme aracı. Daha sonra [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) barındıran sunucuyu yapılandırmak için aracı [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması ve uygun ortam değişkenlerini ayarlayarak .NET bellek profili oluşturma etkinleştirin ve ardından bilgisayarı yeniden başlatın.  
  
 Verileri toplamak için profil oluşturucu başlatın ve ardından hedef uygulama çalıştırın. Profil Oluşturucu uygulamaya bağlı olsa da, duraklatma ve veri toplama sürdürme. Uygun verileri topladığınızda, uygulamayı kapatın, Internet Information Services (IIS) çalışan işlem kapatın ve ardından profil oluşturucuyu kapatın.  
  
 Profil oluşturma iş tamamlandığında, web.config dosyasını ve Web sunucusu özgün durumlarına geri yükleyin.  
  
## <a name="configuring-the-aspnet-web-application-and-the-web-server"></a>ASP.NET Web uygulaması ve Web sunucusu yapılandırma  
  
#### <a name="to-configure-the-aspnet-web-application-and-the-web-server"></a>ASP.NET Web uygulaması ve Web sunucusu yapılandırmak için  
  
1.  Hedef uygulamanın web.config dosyasını değiştirin. Bkz: [nasıl yapılır: Gereci için Web.Config dosyalarını değiştirme ve dinamik olarak derlenmiş ASP.NET Web uygulamalarında profil](../profiling/how-to-modify-web-config-files-to-instrument-and-profile-dynamically-compiled-aspnet-web-applications.md).  
  
2.  Web uygulamasını barındıran bilgisayarda bir komut istemi penceresi açın.  
  
3.  Profil oluşturma ortam değişkenleri başlatır. Tür:  
  
     **VSPerfClrEnv /globaltracegc**  
  
     -veya-  
  
     **VSPerfClrEnv /globaltracegclife**  
  
    -   **/globaltracegc** bellek ayırma verilerin toplanmasını sağlar.  
  
    -   **/globaltracegclife** bellek ayırma verileri ve nesne yaşam verisi koleksiyonunu sağlar.  
  
4.  Bilgisayarı yeniden başlatın.  
  
## <a name="running-the-profiling-session"></a>Profil oluşturma oturumu çalıştırma  
  
#### <a name="to-profile-the-aspnet-web-application"></a>Profil ASP.NET Web uygulaması  
  
1.  Profil Oluşturucu başlatın. Tür:  
  
     **VSPerfCmd** [/start](../profiling/start.md) **: izleme** [/çıkış](../profiling/output.md) **:** `OutputFile` [`Options`]  
  
    -   **/Start:trace** seçeneği profil oluşturucu başlatır.  
  
    -   **/Çıktı:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile` Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     İle aşağıdaki seçeneklerden birini kullanabilirsiniz **/start:trace** seçeneği.  
  
    > [!NOTE]
    >  **/User** ve **/crosssession** seçenekleri ASP.NET uygulamaları için genellikle gerekli.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Sahibi olan hesabın isteğe bağlı etki alanı ve kullanıcı adını belirtir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] çalışan işlemi. İşlem oturum açan kullanıcının başka bir kullanıcı olarak çalışıyorsa, bu seçeneği gereklidir. Adı, Windows Görev Yöneticisi'nin İşlemler sekmesinde kullanıcı adı sütununda listelenir.|  
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturumlarda işlemleri profil oluşturma. Bu seçenek, uygulamanın farklı bir oturumda çalışıyorsa gereklidir. Oturum kimliği, Windows Görev Yöneticisi'nin İşlemler sekmesinde oturum kimliği sütununda listelenir. **/CS** için bir kısaltma olarak belirtilen **/crosssession**.|  
    |[/globaloff](../profiling/globalon-and-globaloff.md)|Profil Oluşturucu veri koleksiyonu duraklatıldı başlatır. Kullanım [/globalon](../profiling/globalon-and-globaloff.md) profil sürdürmek için.|  
    |[/ sayacı](../profiling/counter.md) **:** `Config`|Belirtilen sayaç işlemci performansı bilgi toplar `Config`. Sayaç bilgileri her profil olay, toplanan veriler eklenir.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|  
  
2.  Başlat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması normal şekilde.  
  
## <a name="controlling-data-collection"></a>Veri Toplama Denetimi  
 Hedef uygulama çalışırken, başlatma ve kullanarak profil oluşturucu veri dosyası için veri yazma durdurma tarafından veri toplama denetleyebilirsiniz **VSPerfCmd.exe** seçenekleri. Veri toplama denetimi, program yürütme, başlatılıyor veya uygulama kapatılmadan gibi belirli bir bölümü için veri toplamanıza olanak sağlar.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Seçenekler aşağıdaki çiftleri başlatın ve veri toplama işlemini durdurun. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) işlem kimliği tarafından belirtilen işlem için veri toplama (`PID`).|  
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:** `TID`|Başlatır (**/threadon**) veya durdurulduğunda (**/threadoff**) Kimlikli iş parçacığı tarafından belirtilen iş parçacığı için veri toplama (`TID`).|  
  
-   Aynı zamanda **VSPerfCmd.exe**[/işaretlemek](../profiling/mark.md) profil işareti veri dosyasına eklemek için seçeneği. **/İşaretlemek** komut tanımlayıcı, bir zaman damgası ve bir kullanıcı tanımlı isteğe bağlı bir metin dizesi ekler. İşaretleri Profil Oluşturucusu rapor ve veri görünümleri verilerini filtrelemek için kullanılabilir.  
  
## <a name="ending-the-profiling-session"></a>Profil oluşturma oturumu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için hedef kapatmak [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması, profili işlemini durdurun ve sonra Profil Oluşturucu kapatmak için Internet Information Services (IIS) durdurun. Ardından IIS'yi yeniden başlatın.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Kapat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması.  
  
2.  Kapat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Internet Information Services (IIS) sıfırlama tarafından çalışan işlemi. Tür:  
  
     **IISReset/stop**  
  
3.  Profil Oluşturucu kapatın. Tür:  
  
     **VSPerfCmd** [Shutdown](../profiling/shutdown.md)  
  
4.  IIS'yi yeniden başlatın. Tür:  
  
     **IISReset/Start**  
  
## <a name="restoring-the-application-and-computer-configuration"></a>Uygulama ve bilgisayar yapılandırmasını geri yükleme  
 Tüm profil oluşturmayı tamamladıktan sonra web.config dosyasını değiştirin, profil ortam değişkenleri temizleyin ve sunucuyu geri yüklemek için bilgisayarı yeniden başlatın ve [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] özgün durumlarına uygulama.  
  
#### <a name="to-restore-the-application-and-computer-configuration"></a>Uygulama ve bilgisayar yapılandırmasını geri yüklemek için  
  
1.  Web.config dosyasının özgün dosyanın bir kopyasını değiştirin.  
  
2.  (İsteğe bağlı). Profil oluşturma ortam değişkenleri temizleyin. Tür:  
  
     **VSPerfCmd /globaloff**  
  
3.  Bilgisayarı yeniden başlatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [.NET bellek verisi görünümleri](../profiling/dotnet-memory-data-views.md)