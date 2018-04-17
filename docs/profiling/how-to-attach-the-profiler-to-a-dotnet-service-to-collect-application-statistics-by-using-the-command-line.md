---
title: 'Nasıl yapılır: komut satırını kullanarak uygulama istatistikleri toplamak için bir .NET hizmetine profil oluşturucu ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: a0046c47-26c8-4bec-96a0-81da05e5104a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: c9a89e4c9f14119296f170584919afa135e729e6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-attach-the-profiler-to-a-net-service-to-collect-application-statistics-by-using-the-command-line"></a>Nasıl yapılır: Komut Satırını Kullanarak Uygulama İstatistikleri Toplamak için bir .NET Hizmetine Profil Oluşturucu Ekleme
Bu konuda nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturucuyu bir .NET Framework eklemek için profil oluşturma araçları komut satırı araçları hizmet ve örnekleme yöntemini kullanarak performans istatistikleri toplama.  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
>   
>  Profil oluşturma araçları komut satırı araçları \Team Tools\Performance araçları alt dizininde bulunan [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64 bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
>   
>  Profil oluşturma çalışmaya katman etkileşim verileri ekleme belirli yordamları profil oluşturma araçları komut satırıyla gerektirir. Bkz: [katman etkileşim verileri toplama](../profiling/adding-tier-interaction-data-from-the-command-line.md).  
  
 Bir .NET Framework hizmetinden performans verilerini toplamak için kullanmanız gerekir [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) uygun ortam değişkenlerini başlatmak için araç. Sonra hizmeti barındıran bilgisayarı yeniden başlatın ve profil oluşturma için o bilgisayarın yapılandırmanız gerekir. Ardından hizmet işlemini profil oluşturucu ekleme. Profil Oluşturucu hizmetine eklendiğinde, duraklatma ve veri toplama sürdürme.  
  
 Profil oluşturma oturumunu sonlandırmak için, profil oluşturucunun hizmetten ayrılması ve ve açıkça kapatılması gerekir. Çoğu durumda, bir oturumun sonunda profil ortam değişkenleri temizleme öneririz.  
  
## <a name="attaching-the-profiler"></a>Profil Oluşturucu ekleme  
  
#### <a name="to-attach-the-profiler-to-a-net-framework-service"></a>Profil oluşturucuyu bir .NET Framework hizmetine eklemek için  
  
1.  Hizmetini yükleyin.  
  
2.  Bir komut istemi penceresi açın.  
  
3.  Profil oluşturma ortam değişkenleri başlatır. Tür:  
  
     **VSPerfClrEnv /globalsampleon** [**/samplelineoff**]  
  
    -   **/globalsampleon** örnekleme sağlar.  
  
    -   **/samplelineoff** belirli bir kaynak kod satırı için toplanan verileri atama devre dışı bırakır. Bu seçenek belirtildiğinde, verileri yalnızca işlevleriyle atanır.  
  
4.  Bilgisayarı yeniden başlatın.  
  
5.  Bir komut istemi penceresi açın.  
  
6.  Profil Oluşturucu başlatın. Tür:  
  
     **VSPerfCmd**[/start](../profiling/start.md) **: örnek**[/çıkış](../profiling/output.md) **:** `OutputFile` [`Options`]      
  
    -   **/Start:sample** seçeneği profil oluşturucu başlatır.  
  
    -   **/Çıktı:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile` Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     İle aşağıdaki seçeneklerden birini kullanabilirsiniz **/start:sample** seçeneği.  
  
    > [!NOTE]
    >  **/User** ve **/crosssession** seçenekleri hizmetler için genellikle gerekli.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Profili işleme sahip hesabın etki alanı ve kullanıcı adını belirtir. Bu seçenek, yalnızca işlem oturum açan kullanıcının başka bir kullanıcı olarak çalışıyorsa gereklidir. İşlem sahibi, Windows Görev Yöneticisi'nin İşlemler sekmesinde kullanıcı adı sütununda listelenir.|  
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturumlarda işlemleri profil oluşturma. Farklı bir oturumda Hizmeti çalışıyorsa, bu seçeneği gereklidir. Oturum kimliği, Windows Görev Yöneticisi'nin İşlemler sekmesinde oturum kimliği sütununda listelenir. **/CS** için bir kısaltma olarak belirtilen **/crosssession**.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|  
  
7.  Gerekirse, hizmeti başlatın.  
  
8.  Hizmete profil oluşturucu ekleme. Tür:  
  
     **VSPerfCmd**[/ attach](../profiling/attach.md) **:** {`PID`&#124;`ProcName`} [`Sample Event`] [[/targetclr](../profiling/targetclr.md)**:**`Version`]    
  
    -   İşlem kimliği belirtin (`PID`) veya hizmetin işlem adı (ProcName). Windows Görev Yöneticisi'nde işlem kimlikleri ve adları tüm çalışan işlemleri görüntüleyebilirsiniz.  
  
     Varsayılan olarak, performans verileri her 10,000,000 durdurulamaz harici işlemci saatinin örneklenen döngüleri. 1GH işlemcide saniyede yaklaşık 100 örnek budur. Saat döngüsü aralığını değiştirmek için ya da farklı örnekleme olay belirtmek için aşağıdaki seçeneklerden birini belirtebilirsiniz.  
  
    |Örnek olayı|Açıklama|  
    |------------------|-----------------|  
    |[/Timer](../profiling/timer.md) **:** `Interval`|Örnekleme aralığı tarafından belirtilen durdurulamaz harici saat döngüsü sayısını değiştirir `Interval`.|  
    |[/PF](../profiling/pf.md)[**:**`Interval`]|Örnekleme olay sayfa hataları değiştirir. Varsa `Interval` belirtilmemişse, örnekler arasındaki sayfa hatalarının sayısını ayarlar. Varsayılan 10'dur.|  
    |[/ sys](../profiling/sys-vsperfcmd.md)[`:``Interval`]|Örnekleme olay sistem çağrıları (syscalls) işletim sistemi çekirdeğe işleminden değiştirir. Varsa `Interval` belirtilmemişse, örnekler arasındaki çağrılarının sayısını ayarlar. Varsayılan 10'dur.|  
    |[/ sayacı](../profiling/counter.md) **:** `Config`|Belirtilen aralığı ve işlemci performans sayacı örnekleme olay ve aralığı değişikliklerini `Config`.|  
  
    -   **targetclr:** `Version` bir uygulamada birden fazla çalışma zamanı sürümü yüklendiğinde profiline ortak dil çalışma zamanı (CLR) sürümünü belirtir. İsteğe bağlı.  
  
## <a name="controlling-data-collection"></a>Veri Toplama Denetimi  
 Hizmet çalışırken kullanabileceğiniz **VSPerfCmd.exe** Profil Oluşturucu veri dosyası için veri yazma durdurmak ve başlatmak için Seçenekler. Veri toplama denetimi, program yürütme, başlatılıyor veya uygulama kapatılmadan gibi belirli bir bölümü için veri toplamanıza olanak sağlar.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Aşağıdaki çiftleri **VSPerfCmd** seçenekleri başlatma ve durdurma veri toplama. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) işlem kimliği tarafından belirtilen işlem için veri toplama (`PID`).|  
    |**/ ekleme:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[: {`PID`&#124;`ProcName`}]|**/ attach** işlem kimliği veya işlem adı tarafından belirtilen işlem için veri toplamaya başlar. **/ detach** belirli bir işlemin belirtilmezse, tüm işlemler veya belirtilen işlem için veri toplamayı durdurur.|  
  
## <a name="ending-the-profiling-session"></a>Profil oluşturma oturumu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için profil oluşturucu tüm profili işlemlerini ayrılmış olmalıdır ve profil oluşturucu açıkça kapatılmalıdır. Ayırma örnekleme yöntemi ile uygulama kapatarak veya çağırarak profili uygulamadan **VSPerfCmd / detach** seçeneği. Ardından çağıran **VSPerfCmd shutdown** profil oluşturucu kapatmak ve profil oluşturma veri dosyası kapatmak için seçeneği.  
  
 **VSPerfClrEnv /globaloff** komutu temizler profil ortam değişkenleri, ancak bilgisayar yeniden başlatılana kadar sistem yapılandırması sıfırlanmaz.  
  
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
 [Örnekleme yöntemi veri görünümleri](../profiling/profiler-sampling-method-data-views.md)