---
title: 'Nasıl yapılır: bağımsız bir .NET Framework bileşenini izleme ve komut satırını kullanarak profil oluşturucu ile bellek verileri toplama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: d09cc46a-70f5-48f9-aa24-89913e67b359
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 67899ae042ee6056ab7262a8060890ba0685b502
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815996"
---
# <a name="how-to-instrument-a-stand-alone-net-framework-component-and-collect-memory-data-with-the-profiler-by-using-the-command-line"></a>Nasıl yapılır: bağımsız bir .NET Framework bileşenini izleme ve komut satırını kullanarak profil oluşturucu ile bellek verileri toplama
Bu makalede nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir .exe veya .dll dosyası gibi tek başına bir uygulama, .NET Framework bileşenini izleme için profil oluşturma araçları komut satırı araçları dosya ve Profil Oluşturucu kullanarak bellek bilgiler toplayabilir.  
  
> [!NOTE]
>  Profil oluşturma araçları komut satırı araçları içinde bulunur *\Team Tools\Performance Araçları* Visual Studio yükleme dizininin alt. 64-bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  

  
 İzleme metodunu kullanarak bir .NET Framework bileşenden bellek verileri toplamak için kullandığınız [VSInstr.exe](../profiling/vsinstr.md) bileşenin izleme eklenmiş bir sürümünü oluşturmak için araç ve [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) Profil oluşturma ortam değişkenlerini başlatmak için araç. Sonra kullanarak profil oluşturucu başlatın *VSPerfCmd.exe* aracı.  
  
 İzleme eklenmiş bileşen yürütüldüğünde, bellek verileri bir veri dosyası otomatik olarak toplanır. Duraklatma ve veri toplama sırasında profil oluşturma oturumu sürdürün.  
  
 Profil oluşturma oturumu sona erdirmek için hedef uygulamayı kapatın ve açıkça profil oluşturucuyu kapatın. Çoğu durumda, bir oturumun sonunda profil ortam değişkenleri temizleme öneririz.  
  
## <a name="start-the-application-with-the-profiler"></a>Profil Oluşturucu ile uygulama Başlat  
  
#### <a name="to-attach-the-profiler-to-a-running-net-framework-application"></a>Profil Oluşturucu çalışan bir .NET Framework uygulama eklemek için  
  
1.  Bir komut istemi penceresi açın.  
  
2.  Kullanım **Vsınstr** hedef uygulama izleme eklenmiş bir sürümünü oluşturmak için aracı.  
  
3.  Ortam değişkenleri profil .NET Framework başlatır. Tür:  
  
     **VSPerfClrEnv** {**/tracegc** &#124; **/tracegclife**}  
  
    -   **/Tracegc** ve **/tracegclife** seçenekleri ortam değişkenleri yalnızca bellek ayırma verileri toplamak için veya bellek ayırma ve nesne yaşam süresi verilerini toplamak için başlatılamıyor.  
  
        |Seçenek|Açıklama|  
        |------------|-----------------|  
        |**/tracegc**|Bellek ayırma yalnızca verilerin toplanmasını sağlar.|  
        |**/tracegclife**|Bellek ayırma ve nesne yaşam verisi koleksiyonunu sağlar.|  
  
4.  Profil Oluşturucu başlatın. Tür:  
  
     **VSPerfCmd /start:trace/Output:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md)**: izleme** seçeneği profil oluşturucu başlatır.  
  
    -   [/Çıkış](../profiling/output.md)**:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile` Profil oluşturma verileri konumunu ve adını belirtir (. *Vsp*) dosyası.  
  
     İle aşağıdaki seçeneklerden birini kullanabilirsiniz **/start:trace** seçeneği.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Profili işleme sahip hesabın etki alanı ve kullanıcı adını belirtir. Bu seçenek, yalnızca işlem oturum açmış olan kullanıcı dışındaki bir kullanıcı olarak çalışıyorsa gereklidir. Kullanıcı adı sütununa listelendiğini işlem sahibi **işlemleri** sekmesi Windows Görev Yöneticisi'nin.|  
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturumlarda işlemleri profil oluşturma. Bu seçenek, uygulamanın farklı bir oturumda çalışıyorsa gereklidir. Oturum idenitifer listelenen **oturum kimliği** sütunu **işlemleri** sekmesi Windows Görev Yöneticisi'nin. **/CS** için bir kısaltma olarak belirtilen **/crosssession**.|  
    |[/globaloff](../profiling/globalon-and-globaloff.md)|Profil Oluşturucu ile veri toplama başlatmak için duraklatıldı, ekleme **/globaloff** için seçenek **/start** komut satırı. Kullanım **/globalon** profil sürdürmek için.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|  
    |[/ sayacı](../profiling/counter.md) **:** `Config`|Yapılandırma dosyasında belirtilen işlemci performans sayacı bilgileri toplar. Sayaç bilgileri her profil olay, toplanan verilere eklenir.|  
    |[Olayları](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı bir toplanır (. *etl*) dosyası.|  
  
5.  Hedef uygulama komut istemi penceresinden başlatın.  
  
## <a name="control-data-collection"></a>Veri toplamayı denetleme  
 Hedef uygulama çalışırken, başlatma ve kullanarak verileri dosyaya yazma durdurma tarafından veri toplama denetleyebilirsiniz *VSPerfCmd.exe* seçenekleri. Veri toplama denetimi, program yürütme, başlatılıyor veya uygulama kapatılmadan gibi belirli bir bölümü için veri toplamanıza olanak sağlar.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Aşağıdaki çiftleri **VSPerfCmd** seçenekleri başlatma ve durdurma veri toplama. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon](../profiling/globalon-and-globaloff.md) [/globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) işlem kimliği tarafından belirtilen işlem için veri toplama (`PID`).|  
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:** `TID`|Başlatır (**/threadon**) veya durdurulduğunda (**/threadoff**) Kimlikli iş parçacığı tarafından belirtilen iş parçacığı için veri toplama (`TID`).|  
  
## <a name="end-the-profiling-session"></a>Profil oluşturma oturumunu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için izleme eklenmiş bileşenini çalıştıran uygulamayı kapatın ve ardından arama **VSPerfCmd** [shutdown](../profiling/shutdown.md) profil oluşturucu devre dışı bırakma ve profil oluşturma veri dosyası kapatmak için seçeneği. **VSPerfClrEnv / kapalı** komutu profil ortam değişkenleri temizler.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Hedef uygulamayı kapatın.  
  
2.  Profil Oluşturucu kapatın. Tür:  
  
     **VSPerfCmd Shutdown**  
  
3.  (İsteğe bağlı) Profil oluşturma ortam değişkenleri temizleyin. Tür:  
  
     **VSPerfCmd / kapalı**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Bağımsız uygulamalar profili](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [.NET bellek verisi görünümleri](../profiling/dotnet-memory-data-views.md)