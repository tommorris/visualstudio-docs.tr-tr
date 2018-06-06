---
title: 'Nasıl yapılır: komut satırını kullanarak bellek verileri toplamak için bağımsız bir .NET Framework uygulamasına Profil Oluşturucu ile başlatma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 3bc53041-91b7-4ad0-8413-f8bf2c4b3f5e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 3d1cbc108bbe48377b34683436f4796ac377ef82
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815515"
---
# <a name="how-to-launch-a-stand-alone-net-framework-application-with-the-profiler-to-collect-memory-data-by-using-the-command-line"></a>Nasıl yapılır: komut satırını kullanarak bellek verileri toplamak için bağımsız bir .NET Framework uygulamasını Profil Oluşturucu ile başlatma
Bu konuda nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir .NET Framework tek başına (istemci) uygulamasını başlatın ve bellek verileri toplamak için profil oluşturma araçları komut satırı araçları.  
  
 Profil oluşturma oturumu üç bölümden oluşur:  
  
-   Profil Oluşturucu kullanarak uygulama başlatma.  
  
-   Profil oluşturma veri toplama.  
  
-   Profil oluşturma oturumu sona erdirme.  
  
> [!NOTE]
>  Profil oluşturma araçları komut satırı araçları içinde bulunur *\Team Tools\Performance Araçları* alt [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64-bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
## <a name="start-the-application-with-the-profiler"></a>Profil Oluşturucu ile uygulama Başlat  
 Profil Oluşturucu kullanarak bir hedef uygulama başlatmak için kullandığınız **VSPerfCmd.exe/start** ve **/başlatma** profil oluşturucu başlatın ve uygulamayı başlatmak için Seçenekler. Belirleyebileceğiniz **/start** ve **/başlatma** ve bunlara karşılık gelen seçenekleri bir komut satırında.  
  
 Ayrıca ekleyebileceğiniz **/globaloff** hedef uygulama başlangıcında veri toplamayı duraklatmak için Seçenekler. Daha sonra **/globalon** veri toplamaya başlamak için.  
  
#### <a name="to-start-an-application-by-using-the-profiler"></a>Profil Oluşturucu kullanarak bir uygulamayı başlatmak için  
  
1.  Bir komut istemi penceresi açın.  
  
2.  Profil Oluşturucu başlatın. Tür:  
  
     **VSPerfCmd /start:sample/Output:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md)**: örnek** seçeneği profil oluşturucu başlatır.  
  
    -   [/Çıkış](../profiling/output.md)**:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile` Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     İle aşağıdaki seçeneklerden birini kullanabilirsiniz **/start:sample** seçeneği.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|  
  
3.  Hedef uygulama başlatın. Tür:  
  
     **VSPerfCmd**[/başlatma](../profiling/launch.md) **:** `appName` **/gc:**{**ayırma**&#124;**yaşam süresi** }[`Options`]  
  
    -   [/Gc](../profiling/gc-vsperfcmd.md)**:** `Keyword` seçeneği, .NET Framework bellek verileri toplamak için gereklidir. Anahtar sözcüğü parametre bellek ayırma verileri toplamak için veya bellek ayırma ve nesne yaşam süresi verilerini toplamak için belirtir.  
  
        |Anahtar sözcüğü|Açıklama|  
        |-------------|-----------------|  
        |**Ayırma**|Bellek ayırma yalnızca veri toplar.|  
        |**Yaşam süresi**|Bellek ayırma ve nesne yaşam verisi toplar.|  
  
     İle aşağıdaki seçeneklerden birini kullanabilirsiniz **/başlatma** seçeneği.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/args](../profiling/args.md) **:** `Arguments`|Hedef uygulamaya geçirilecek komut satırı bağımsız değişkenleri içeren bir dize belirtir.|  
    |[/ Console](../profiling/console.md)|Hedef komut satırı uygulaması ayrı bir pencerede başlatır.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|  
    |[/targetclr](../profiling/targetclr.md) **:** `Version`|Ortak dil çalışma zamanı (CLR) bir uygulamada birden fazla çalışma zamanı sürümü yüklendiğinde profilini sürümünü belirtir.|  
  
## <a name="control-data-collection"></a>Veri toplamayı denetleme  
 Hedef uygulama çalışırken, başlatma ve kullanarak verileri dosyaya yazma durdurma tarafından veri toplama denetleyebilirsiniz *VSPerfCmd.exe* seçenekleri. Veri toplama denetimi, program yürütme, başlatılıyor veya uygulama kapatılmadan gibi belirli bir bölümü için veri toplamanıza olanak sağlar.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Seçenekler aşağıdaki çiftleri başlatın ve veri toplama işlemini durdurun. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) işlem kimliği tarafından belirtilen işlem için veri toplama (`PID`).|  
    |[/ attach](../profiling/attach.md) **:** `PID` [/ Ayır](../profiling/detach.md)|**/ attach** tarafından belirtilen işlem için veri toplamaya başlar `PID` (işlem kimliği). **/ detach** tüm işlemler için veri toplamayı durdurur.|  
  
-   Aynı zamanda **VSPerfCmd.exe**[/işaretlemek](../profiling/mark.md) profil işareti veri dosyasına eklemek için seçeneği. **/İşaretlemek** komut tanımlayıcı, bir zaman damgası ve bir kullanıcı tanımlı isteğe bağlı bir metin dizesi ekler. İşaretleri verilerini filtrelemek için kullanılabilir.  
  
## <a name="end-the-profiling-session"></a>Profil oluşturma oturumunu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için profil oluşturucu tüm profili işlemlerini ayrılmış olmalıdır ve profil oluşturucu açıkça kapatılmalıdır. Profil Oluşturucu uygulamadan uygulama kapatarak veya çağırarak örnekleme yöntemini kullanarak profili ayırabilirsiniz **VSPerfCmd / detach** seçeneği. Ardından çağıran **VSPerfCmd shutdown** profil oluşturucu devre dışı bırakma ve profil oluşturma veri dosyası kapatmak için seçeneği. **VSPerfClrEnv / kapalı** komutu profil ortam değişkenleri temizler.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Profil Oluşturucu hedef uygulamasından ayırmak için aşağıdaki adımlardan birini gerçekleştirin:  
  
    -   Hedef uygulamayı kapatın.  
  
         veya  
  
    -   Tür **VSPerfCmd / Ayır**  
  
2.  Profil Oluşturucu kapatın. Tür:  
  
     **VSPerfCmd**[Shutdown](../profiling/shutdown.md)  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Bağımsız uygulamalar profili](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [.NET bellek verisi görünümleri](../profiling/dotnet-memory-data-views.md)