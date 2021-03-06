---
title: 'Nasıl yapılır: Profiler bir .NET Framework bağımsız uygulamasına ekleme ve komut satırını kullanarak uygulama istatistikleri toplama | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b62fcbc1-791f-474e-890a-a6c332e0c9ea
caps.latest.revision: 39
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f8e2d186fbd0d3226ee3a1b023345ea8369cb627
ms.sourcegitcommit: d705e015cb525bfa87a0b93e93376c3956ec2707
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43231149"
---
# <a name="how-to-attach-the-profiler-to-a-net-framework-stand-alone-application-and-collect-application-statistics-by-using-the-command-line"></a>Nasıl yapılır: Komut Satırını Kullanarak Profil Oluşturucuyu bir .NET Framework Bağımsız Uygulamasına Ekleme ve Uygulama İstatistikleri Toplama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: komut satırını kullanarak bir .NET Framework tek başına uygulama ve uygulama istatistikleri toplamak için Profiler ekleme](https://docs.microsoft.com/visualstudio/profiling/how-to-attach-the-profiler-to-a-dotnet-framework-stand-alone-application-and-collect-application-statistics-by-using-the-command-line).  
  
Bu konu nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] çalışan bir .NET Framework bağımsız (istemci) uygulamasına profil oluşturucu ekleme ve örnekleme yöntemini kullanarak performans istatistikleri toplamak için profil oluşturma araçları komut satırı araçları.  
  
> [!NOTE]
>  Windows 8 ve Windows Server 2012'deki Gelişmiş güvenlik özellikleri Visual Studio profil oluşturucu bu platformlarda veri toplayan bir şekilde önemli değişiklikler gerekmiştir. Windows Store apps ayrıca yeni toplama teknikleri gerektirir. Bkz: [Windows 8 ve Windows Server 2012 uygulamalarında performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
>   
>  Profil araçlarının komut satırı araçları tools\performance Tools alt dizininde içinde bulunan [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] yükleme dizini. 64-bit bilgisayarlarda araçların 64-bit hem 32-bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresinin PATH ortam değişkenine ekleyin veya komutun kendisine eklemeniz gerekir. Daha fazla bilgi için [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
>   
>  Bir profil oluşturma yürütmesine katman etkileşim verileri ekleme, komut satırı profil araçlarıyla özel yordamlar gerektirir. Bkz: [katman etkileşim verileri toplama](../profiling/adding-tier-interaction-data-from-the-command-line.md).  
  
 Hedef uygulama başlamadan önce bir .NET Framework uygulamasından performans verilerini toplamak için uygun ortam değişkenleri başlatılmalıdır. Profil Oluşturucu uygulamaya eklendiğinde, duraklatma ve veri koleksiyonu devam ettirin.  
  
 Profil oluşturma oturumunu sona erdirmek için profil oluşturucu artık uygulamaya bağlı gerekir ve profil oluşturucu açıkça kapatılmalıdır. Çoğu durumda, profil oluşturma oturumunun sonunda profil oluşturma ortam değişkenlerini temizlemenizi öneririz.  
  
## <a name="attaching-the-profiler"></a>Profiler ekleme  
  
#### <a name="to-attach-the-profiler-to-a-running-net-framework-application"></a>Profiler çalışan bir .NET Framework uygulamasına eklemek için  
  
1.  Bir komut istemi penceresi açın.  
  
2.  Profil oluşturma ortamı değişkenlerini başlatın. Tür:  
  
     **VSPerfClrEnv /sampleon** [**/samplelineoff**]  
  
    -   **/Samplelineoff** seçeneği, kaynak kod satır sayısı veri koleksiyonunu devre dışı bırakır.  
  
3.  Profil oluşturucuyu başlatın. Tür:  
  
     **VSPerfCmd /start:sample/Output:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md)**: örnek** seçeneği profil oluşturucuyu başlatır.  
  
    -   [/Output](../profiling/output.md)**:** `OutputFile` ile seçeneği gereklidir **/start**. `OutputFile` Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     Aşağıdaki seçenekler herhangi birini kullanabilirsiniz **/start:sample** seçeneği.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Profilli işlemin sahibi olan hesabının isteğe bağlı etki alanı ve kullanıcı adını belirtir. Oturum açan kullanıcının farklı bir kullanıcı olarak profillenen uygulama yalnızca başlatıldı, bu seçenek gereklidir.|  
    |[/ crosssession](../profiling/crosssession.md)|Etkinleştirir işlemleri diğer oturum açılışlarında profil oluşturma. **/CS** için bir kısaltma olarak belirtilebilir **/crosssession**. Bu seçenek, başka bir oturumda uygulama çalışıyorsa gereklidir.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında Tahsil edilecek Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullanma **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. 500 ms varsayılandır.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında Tahsil edilecek bir olay izleme için Windows (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|  
  
4.  Gerekirse, hedef uygulama normal şekilde başlatın.  
  
5.  Profil Oluşturucu hedef uygulamaya iliştirin. Tür:  
  
     **VSPerfCmd / ekleme:**{`PID`&#124;`ProcessName`} [`Sample Event`] [**/targetclr:**`Version`]  
  
    -   `PID` hedef uygulamanın işlem Kimliğini belirtir. `ProcessName` işlemin adını belirtir. Belirttiğiniz gerçekleştiriyorsanız `ProcessName` ve aynı ada sahip birden çok işlem çalışıyorsa, sonuçların tahmin edilemeyeceğine. Windows Görev Yöneticisi'nde, işlem kimliklerini çalışan tüm işlemlerin görüntüleyebilirsiniz.  
  
    -   [/ targetclr](../profiling/targetclr.md) **:** `Version` bir uygulamada birden fazla çalışma zamanı sürümü yüklendiğinde profiline ortak dil çalışma zamanı (CLR) sürümünü belirtir. İsteğe bağlı.  
  
    -   Varsayılan olarak, performans verisi her 10.000.000 durdurulmamış işlemci saat örneklenen döngüsü. Yaklaşık bir saat 10 saniyede bir adet 1GH işlemcide budur. Saat döngüsü aralığı değiştirmek veya farklı örnekleme olayı belirtmek için aşağıdaki seçeneklerden birini belirtebilirsiniz. [/targetclr](../profiling/targetclr.md)**:** `Version` bir uygulamada birden fazla çalışma zamanı sürümü yüklendiğinde profiline CLR'nin sürümünü belirtir. İsteğe bağlı.  
  
    |||  
    |-|-|  
    |Örnek olay|Açıklama|  
    |[/ Timer](../profiling/timer.md) **:** `Interval`|Örnekleme aralığı tarafından belirtilen durdurulmamış saati döngüleri sayısını değiştirir `Interval`.|  
    |[/PF](../profiling/pf.md) [**:**`Interval`]|Örnekleme olay sayfa hataları değiştirir. Varsa `Interval` belirtilmemişse, örnekler arasında sayfa hatalarının sayısını ayarlar. Varsayılan 10'dur.|  
    |[/ sys](../profiling/sys-vsperfcmd.md) [**:**`Interval`]|Örnekleme olayını, işletim sisteminin çekirdeğine (syscalls) işlemden sisteme çağrı yapmak değiştirir. Varsa `Interval` belirtilmemişse, örnekler arasındaki çağrıların sayısını ayarlar. Varsayılan 10'dur.|  
    |[/ Sayaç](../profiling/counter.md) **:** `Config`|İşlemci performans sayacı ve belirtilen aralık için örnekleme olay ve aralığını değiştirir `Config`.|  
  
    -  
  
## <a name="controlling-data-collection"></a>Veri Toplama Denetimi  
 Hedef uygulama çalışırken, Profil Oluşturucu veri dosyasına verilerin yazılmasını kullanarak durdurmayla ve veri toplamayı kontrol edebilirsiniz **VSPerfCmd.exe** seçenekleri. Veri toplama denetimi uygulamayı kapatma veya başlatma gibi program yürütmenin özel bir bölümü için veri toplamanızı sağlar.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak  
  
-   Aşağıdaki seçenekleri çiftlerini başlatın ve veri toplama işlemini durdurun. Her seçeneği ayrı bir komut satırında belirtin. Veri Toplama'ı, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlar (**/globalon**) veya durdurur (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlar (**/processon**) veya durdurur (**/processoff**) tarafından belirtilen işlem için veri toplamayı `PID`.|  
    |[/ ekleme](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ ekleme** tarafından belirtilen işlem için veri toplamaya başlar `PID` veya işlem adı (ProcName). **/ detach** belirli bir işlem belirtilmezse, belirtilen işlem için veya tüm işlemler için veri toplamayı durdurur.|  
  
## <a name="ending-the-profiling-session"></a>Profil Araçları oturumunu sonlandırma  
 Profil oluşturma oturumunu sona erdirmek için profil oluşturucu oluşturulmuş tüm işlemlerden ayrılması ve profil oluşturucu açıkça kapatılmalıdır. Uygulamayı kapatarak veya çağırarak örnekleme yöntemini kullanarak profili oluşturulmuş bir uygulamadaki profil oluşturucuyu ayırabilirsiniz **VSPerfCmd / detach** seçeneği. Ardından çağırın **VSPerfCmd/shutdown** profil oluşturucuyu kapatmak ve profil oluşturma veri dosyasını kapatırsınız. **VSPerfClrEnv / off** komutu profil oluşturma ortam değişkenlerini temizler.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumunu sona erdirmek için  
  
1.  Hedef uygulamadaki profil oluşturucuyu ayırmak için aşağıdaki adımlardan birini gerçekleştirin:  
  
    -   Tür **VSPerfCmd / detach**  
  
         veya  
  
    -   Hedef uygulamayı kapatın.  
  
2.  Profil oluşturucuyu kapatın. Tür:  
  
     **VSPerfCmd** [ /Shutdown](../profiling/shutdown.md)  
  
3.  (İsteğe bağlı) Profil oluşturma ortam değişkenlerini temizleyin. Tür:  
  
     **VSPerfClrEnv / kapatma**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Örnekleme Yöntemi Veri Görünümleri](../profiling/profiler-sampling-method-data-views.md)



