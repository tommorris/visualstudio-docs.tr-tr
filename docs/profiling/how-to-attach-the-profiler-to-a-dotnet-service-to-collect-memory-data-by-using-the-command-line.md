---
title: 'Nasıl yapılır: komut satırını kullanarak bellek verileri toplamak için bir .NET hizmetine profil oluşturucu ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: aeac39af-ad99-479f-aa36-4104356ca512
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 84e5505b077d4d237ed8f8b2532b4ac2b48544d5
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-attach-the-profiler-to-a-net-service-to-collect-memory-data-by-using-the-command-line"></a>Nasıl yapılır: Komut Satırını Kullanarak Bellek Verileri Toplamak için bir .NET Hizmetine Profil Oluşturucu Ekleme
Bu konuda nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] için profil oluşturucu ekleme için profil oluşturma araçları komut satırı araçları bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] hizmet ve bellek verileri toplama. Bellek ayırmalarının sayısı ve boyutu hakkında veri toplayabilir ve ayrıca, bellek nesnelerinin yaşam süresi hakkında veri toplayabilirsiniz.  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
> [!NOTE]
>  Profil oluşturma araçları komut satırı araçları \Team Tools\Performance araçları alt dizininde bulunan [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64 bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Bellek verileri toplamak için bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] hizmeti, kullandığınız [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) Aracı hizmeti barındıran bilgisayardaki uygun ortam değişkenlerini başlatılamadı. Bilgisayarın, profil oluşturma için yapılandırılmak üzere yeniden başlatılması gerekir.  
  
 Daha sonra [VSPerfCmd](../profiling/vsperfcmd.md) aracı hizmetini işleme profil oluşturucu ekleyin. Hizmete profil oluşturucu eklenirken, duraklatma ve veri toplama sürdürme.  
  
 Profil oluşturma oturumunu sonlandırmak için, profil oluşturucunun hizmetten ayrılması ve ve açıkça kapatılması gerekir. Çoğu durumda, bir oturumun sonunda profil ortam değişkenleri temizleme öneririz.  
  
## <a name="attaching-the-profiler"></a>Profil Oluşturucu ekleme  
  
#### <a name="to-attach-the-profiler-to-a-net-framework-service"></a>Profil oluşturucuyu bir .NET Framework hizmetine eklemek için  
  
1.  Gerekirse, hizmetini yükleyin.  
  
2.  Bir komut istemi penceresi açın.  
  
3.  Profil oluşturma ortam değişkenleri başlatır. Tür:  
  
     **VSPerfClrEnv** {**/globalsamplegc /globalsamplegclife**} [**/samplelineoff**]  
  
    -   Seçenekleri **/globalsamplegclife** ve **/globalsamplegclife** bellek verileri toplamak için türünü belirtin. Aşağıdaki seçeneklerden bir ve yalnızca bir tanesini belirtin.  
  
     **/globalsamplegc**  
     Bellek ayırma verilerinin toplanmasını etkinleştirir.  
  
     **/globalsamplegclife**  
     Bellek ayırma verilerinin ve nesne yaşam süresi verilerinin toplanmasını etkinleştirir.  
  
    -   **/Samplelineoff** seçeneği, kaynak kodu satır numarası veri koleksiyonunu devre dışı bırakır.  
  
4.  Yeni ortam yapılandırmasını ayarlamak için bilgisayarı yeniden başlatın.  
  
5.  Gerekirse, hizmeti başlatın.  
  
6.  Bir komut istemi penceresi açın. Gerekirse, profil oluşturucu yolunu PATH ortam değişkenine ekleyin.  
  
7.  Profil Oluşturucu başlatın. Tür:  
  
     **VSPerfCmd**[/start](../profiling/start.md) **: örnek**[/çıkış](../profiling/output.md) **:** `OutputFile` [`Options`]      
  
    -   **/Start:sample** seçeneği profil oluşturucu başlatır.  
  
    -   **/Çıktı:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile` Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     Bir veya daha fazla ile aşağıdaki seçenekleri kullanabilirsiniz **/start:sample** seçeneği.  
  
    > [!NOTE]
    >  **/User** ve **/crosssession** seçenekleri hizmetler için genellikle gerekli.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|İşlemin sahibi olan hesabının etki alanını ve kullanıcı adını belirtir. İşlem oturum açan kullanıcının başka bir kullanıcı olarak çalışıyorsa, bu seçeneği gereklidir. İşlem sahibi, Windows Görev Yöneticisi'nin İşlemler sekmesinde kullanıcı adı sütununda listelenir.|  
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturum açma oturumları işlemleri profil oluşturma. ASP.NET uygulamasını farklı bir oturumda çalışıyorsa, bu seçeneği gereklidir. Oturum kimliği, Windows Görev Yöneticisi'nin İşlemler sekmesinde oturum kimliği sütununda listelenir. **/CS** için bir kısaltma olarak belirtilen **/crosssession**.|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Hizmetin altında çalıştığı oturum açma hesabının kullanıcı adını ve isteğe bağlı etki alanını belirtir. Oturum açma hesabın, Windows Hizmet Denetimi Yöneticisi'nde hizmetin Farklı Oturum Aç sütununda listelenir.|  
    |[/crosssession&#124;cs](../profiling/crosssession.md)|Etkinleştirir, diğer oturum açma oturumları işlemleri profil oluşturma.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|  
  
8.  Hizmete profil oluşturucu ekleme. Tür:  
  
     **VSPerfCmd**[/ attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [[/targetclr](../profiling/targetclr.md)**:**`Version`]    
  
    -   İşlem kimliğini veya hizmetin işlem adını belirtin. Windows Görev Yöneticisi'nde işlem kimlikleri ve adları tüm çalışan işlemleri görüntüleyebilirsiniz.  
  
    -   **targetclr:** `Version` bir uygulamada birden fazla çalışma zamanı sürümü yüklendiğinde profiline ortak dil çalışma zamanı (CLR) sürümünü belirtir. İsteğe bağlı.  
  
## <a name="controlling-data-collection"></a>Veri Toplama Denetimi  
 Hizmet çalışırken kullanabileceğiniz **VSPerfCmd.exe** seçenekleri durdurun ve verileri Profil Oluşturucu veri dosyasına yazmaya başlayın. Veri toplamanın denetlenmesi, program yürütmenin, uygulamanın başlatılması veya kapatılması gibi özel bir bölümü için veri toplamanızı sağlar.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Aşağıdaki çiftleri **VSPerfCmd** seçenekleri başlatma ve durdurma veri toplama. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) işlem kimliği tarafından belirtilen işlem için veri toplama (`PID`).|  
    |**/ ekleme:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[: {`PID`&#124;`ProcName`}]|**/ attach** işlem kimliği veya işlem adı tarafından belirtilen işlem için veri toplamaya başlar. **/ detach** belirli bir işlemin belirtilmezse, belirtilen işlem için ya da tüm işlemler için veri toplamayı durdurur.|  
  
## <a name="ending-the-profiling-session"></a>Profil oluşturma oturumu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için Profil Oluşturucu veri toplamadığı gerekir. Bir uygulama ile örnekleme yöntemini çağırarak veya hizmetin durdurulması tarafından profili veri toplamayı Durdur **VSPerfCmd / detach** seçeneği. Ardından çağıran **VSPerfCmd** [shutdown](../profiling/shutdown.md) profil oluşturucu kapatmak ve profil oluşturma veri dosyası kapatmak için seçeneği. **VSPerfClrEnv /globaloff** komutu temizler profil ortam değişkenleri, ancak bilgisayar yeniden başlatılana kadar sistem yapılandırması sıfırlanmaz.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Profil Oluşturucu hedef uygulamasından ayırmak için aşağıdakilerden birini yapın:  
  
    -   Hizmetini durdurun.  
  
         -veya-  
  
    -   Tür **VSPerfCmd / Ayır**  
  
2.  Profil Oluşturucu kapatın. Tür:  
  
     **VSPerfCmd Shutdown**  
  
3.  (İsteğe bağlı) Profil oluşturma ortam değişkenleri temizleyin. Tür:  
  
     **VSPerfClrEnv /globaloff**  
  
4.  Bilgisayarı yeniden başlatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)   
 [.NET bellek verisi görünümleri](../profiling/dotnet-memory-data-views.md)