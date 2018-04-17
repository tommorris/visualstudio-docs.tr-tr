---
title: 'Nasıl yapılır: komut satırını kullanarak uygulama istatistikleri toplamak için bir yerel hizmete profil oluşturucu ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: f783817f-77a0-4eb8-985b-ec3b77eadc42
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 375d0eb5a50adf63b7a9c312b824579c75a50459
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-attach-the-profiler-to-a-native-service-to-collect-application-statistics-by-using-the-command-line"></a>Nasıl yapılır: Komut Satırını Kullanarak Uygulama İstatistikleri Toplamak için bir Yerel Hizmete Profil Oluşturucu Ekleme
Bu konuda nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir yerel hizmete profil oluşturucu ekleme ve örnekleme yöntemini kullanarak performans istatistikleri toplamak için profil oluşturma araçları komut satırı araçları.  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
> [!NOTE]
>  Profil oluşturma araçları komut satırı araçları \Team Tools\Performance araçları alt dizininde bulunan [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64 bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Hizmete profil oluşturucu eklenirken, duraklatma ve veri toplama sürdürme.  
  
 Profil oluşturma oturumunu sonlandırmak için, profil oluşturucunun hizmetten ayrılması ve ve açıkça kapatılması gerekir.  
  
## <a name="starting-the-application-with-the-profiler"></a>Profil Oluşturucu ile uygulama başlatma  
 Bir yerel hizmete profil oluşturucu ekleme için kullandığınız **VSPerfCmd.exe**[/start](../profiling/start.md) ve [/ attach](../profiling/attach.md) profil oluşturucu başlatmak ve hedef uygulamaya eklemek için Seçenekler. Belirleyebileceğiniz **/start** ve **/ attach** ve bunlara karşılık gelen seçenekleri tek bir komut satırında. Ayrıca ekleyebileceğiniz [/globaloff](../profiling/globalon-and-globaloff.md) hedef uygulama başlangıcında veri toplamayı duraklatmak için seçeneği. Daha sonra [/globalon](../profiling/globalon-and-globaloff.md) verileri toplamaya başlamak için.  
  
#### <a name="to-attach-the-profiler-to-a-native-service"></a>Bir yerel hizmete profil oluşturucu eklemek için  
  
1.  Gerekirse, hizmeti başlatın.  
  
2.  Bir komut istemi penceresi açın.  
  
3.  Profil Oluşturucu başlatın. Tür:  
  
     **VSPerfCmd /start:sample**[/çıkış](../profiling/output.md) **:** `OutputFile` [`Options`]    
  
    -   **/Start:sample** seçeneği profil oluşturucu başlatır.  
  
    -   **/Çıktı:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile` Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     İle aşağıdaki seçeneklerden birini kullanabilirsiniz **/start:sample** seçeneği.  
  
    > [!NOTE]
    >  **/User** ve **/crosssession** seçenekleri hizmetler için genellikle gerekli.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Profili işleme sahip hesabın etki alanı ve kullanıcı adını belirtir. Bu seçenek, yalnızca işlem oturum açan kullanıcının başka bir kullanıcı olarak çalışıyorsa gereklidir. İşlem sahibi, Windows Görev Yöneticisi'nin İşlemler sekmesinde kullanıcı adı sütununda listelenir.|  
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturumlarda işlemleri profil oluşturma. Bu seçenek, uygulamanın farklı bir oturumda çalışıyorsa gereklidir. Oturum kimliği, Windows Görev Yöneticisi'nin İşlemler sekmesinde oturum kimliği sütununda listelenir. **/CS** için bir kısaltma olarak belirtilen **/crosssession**.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|  
  
4.  Hizmete profil oluşturucu ekleme. Tür:  
  
     **VSPerfCmd / ekleme:** `PID` [`Sample Event`]  
  
     `PID` Hedef uygulama işlem Kimliğini belirtir. İşlem tüm çalışan işlemleri kimliklerini Windows Görev Yöneticisi'nde görüntüleyebilirsiniz.  
  
     Varsayılan olarak, performans verileri her 10,000,000 durdurulamaz harici işlemci saatinin örneklenen döngüleri. 10 saniyede yaklaşık bir kez 1GH işlemcide budur. Saat döngüsü aralığını değiştirmek için ya da farklı örnekleme olay belirtmek için aşağıdaki seçeneklerden birini belirtebilirsiniz.  
  
    |Örnek olayı|Açıklama|  
    |------------------|-----------------|  
    |[/Timer](../profiling/timer.md) **:** `Interval`|Örnekleme aralığı tarafından belirtilen durdurulamaz harici saat döngüsü sayısını değiştirir `Interval`.|  
    |[/PF](../profiling/pf.md)[**:**`Interval`]|Örnekleme olay sayfa hataları değiştirir. Varsa `Interval` belirtilmemişse, örnekler arasındaki sayfa hatalarının sayısını ayarlar. Varsayılan 10'dur.|  
    |[/ sys](../profiling/sys-vsperfcmd.md) [**:**`Interval`]|Örnekleme olay sistem çağrıları (syscalls) işletim sistemi çekirdeğe işleminden değiştirir. Varsa `Interval` belirtilmemişse, örnekler arasındaki çağrılarının sayısını ayarlar. Varsayılan 10'dur.|  
    |[/ sayacı](../profiling/counter.md) **:** `Config`|Belirtilen aralığı ve işlemci performans sayacı örnekleme olay ve aralığı değişikliklerini `Config`.|  
  
## <a name="controlling-data-collection"></a>Veri Toplama Denetimi  
 Hedef uygulama çalışırken, kullanabileceğiniz **VSPerfCmd.exe** Profil Oluşturucu veri dosyası için veri yazma durdurmak ve başlatmak için Seçenekler. Veri toplama denetimi, program yürütme, başlatılıyor veya uygulama kapatılmadan gibi belirli bir bölümü için veri toplamanıza olanak sağlar.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Aşağıdaki çiftleri **VSPerfCmd** seçenekleri başlatma ve durdurma veri toplama. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) işlem kimliği tarafından belirtilen işlem için veri toplama (`PID`).|  
    |**/ ekleme:** {`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[: {`PID`&#124;`ProcName`}]|**/ attach** işlem kimliği veya işlem adı tarafından belirtilen işlem için veri toplamaya başlar. **/ detach** bir işlem belirtilmezse, belirtilen işlem için ya da tüm işlemler için veri toplamayı durdurur.|  
  
## <a name="ending-the-profiling-session"></a>Profil oluşturma oturumu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için profil oluşturucu hizmetinden ayrılmış ve açıkça kapatılmalıdır. Hizmetin durdurulması veya arayarak örnekleme yöntemiyle profili yerel hizmete ayırabilirsiniz **VSPerfCmd / detach** seçeneği. Ardından çağıran **VSPerfCmd** [shutdown](../profiling/shutdown.md) profil oluşturucu kapatmak ve profil oluşturma veri dosyası kapatmak için seçeneği.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Profil Oluşturucu hedef uygulamasından ayırmak için aşağıdakilerden birini yapın:  
  
    -   Hizmetini durdurun.  
  
         -veya-  
  
    -   Tür **VSPerfCmd / Ayır**  
  
2.  Profil Oluşturucu kapatın. Tür:  
  
     **VSPerfCmd Shutdown**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)   
 [Örnekleme yöntemi veri görünümleri](../profiling/profiler-sampling-method-data-views.md)