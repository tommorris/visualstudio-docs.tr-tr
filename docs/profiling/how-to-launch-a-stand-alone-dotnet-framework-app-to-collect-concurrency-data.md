---
title: 'Nasıl yapılır: komut satırını kullanarak eşzamanlılık verileri toplamak için bağımsız bir .NET Framework uygulamasına Profil Oluşturucu ile başlatma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 17a48848-bd3e-44ef-9971-e39836ff1df2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 6d194ddfb83570b4e2a5461dc70a0368215aaca5
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
---
# <a name="how-to-launch-a-stand-alone-net-framework-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line"></a>Nasıl yapılır: Komut Satırını Kullanarak Eşzamanlılık Verileri Toplamak için Bağımsız bir .NET Framework Uygulamasını Başlatma
Bu konuda nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir .NET Framework tek başına (istemci) uygulamasını başlatın ve işlemi ve iş parçacığı eşzamanlılık verileri toplamak için profil oluşturma araçları komut satırı araçları  
  
> [!NOTE]
>  Profil oluşturma araçları komut satırı araçları \Team Tools\Performance araçları alt dizininde bulunan [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64 bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Profil Oluşturucu uygulamaya bağlı olsa da, duraklatma ve veri toplama sürdürme. Profil oluşturma oturumu sona erdirmek için profil oluşturucu artık uygulamaya bağlı olması gerekir ve profil oluşturucu açıkça kapatılmalıdır.  
  
## <a name="starting-the-application-with-the-profiler"></a>Profil Oluşturucu ile uygulama başlatma  
 Bir .NET Framework hedef uygulamayı başlatmak için .NET Framework'te profil oluşturma değişkenleri ayarlamak için VSPerfClrEnv.exe kullanın. Ardından VSPerfCmd kullandığınız **/start** ve **/başlatma** profil oluşturucu başlatın ve uygulamayı başlatmak için Seçenekler. Belirleyebileceğiniz **/start** ve **/başlatma** ve bunların ilgili tek bir komut satırı seçenekleri. Ayrıca ekleyebileceğiniz **/globaloff** hedef uygulama başlatıldığında veri toplamayı duraklatmak için komut satırı seçeneği. Daha sonra **/globalon** veri toplamaya başlamak için ayrı bir komut satırında.  
  
#### <a name="to-start-an-application-with-the-profiler"></a>Profil Oluşturucu ile bir uygulamayı başlatmak için  
  
1.  Bir komut istemi penceresi açın.  
  
2.  Profil Oluşturucu başlatın. Tür:  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency**[**,**{**ResourceOnly**&#124;**ThreadOnly**}] **/ Çıkış:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md) seçeneği profil oluşturucu başlatır.  
  
        |||  
        |-|-|  
        |**/Start:concurrency**|Kaynak çakışması ve iş parçacığı yürütme veri toplanmasını sağlar.|  
        |**/Start:concurrency, resourceonly**|Yalnızca kaynak çakışması veri toplanmasını sağlar.|  
        |**/Start:concurrency, threadonly**|Yalnızca iş parçacığı yürütme veri toplanmasını sağlar.|  
  
    -   [/Çıkış](../profiling/output.md)**:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile` Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     İle aşağıdaki seçeneklerden birini kullanabilirsiniz **/start:concurrency** seçeneği.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`domain\`]`username`|Profil Oluşturucu için erişim verilecek hesabın kullanıcı adını ve isteğe bağlı etki alanını belirtir.|  
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturum açma oturumları işlemleri profil oluşturma.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|  
  
3.  Hedef uygulama başlatın. Tür:  
  
     **VSPerfCmd**[/başlatma](../profiling/launch.md) **:** `AppName` [`Options`] [`Sample Event`]  
  
     İle aşağıdaki seçeneklerden birini kullanabilirsiniz **/başlatma** seçeneği.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/args](../profiling/args.md) **:** `Arguments`|Hedef uygulamaya geçirilecek komut satırı bağımsız değişkenleri içeren bir dize belirtir.|  
    |[/ Console](../profiling/console.md)|Hedef komut satırı uygulaması ayrı bir pencerede başlatır.|  
    |[/targetclr](../profiling/targetclr.md) **:** `Version`|Ortak dil çalışma zamanı (CLR) bir uygulamada birden fazla çalışma zamanı sürümü yüklendiğinde profilini sürümünü belirtir.|  
  
## <a name="controlling-data-collection"></a>Veri Toplama Denetimi  
 Hedef uygulama çalışırken, başlatma ve VSPerfCmd.exe seçenekleri kullanarak verileri dosyaya yazma durdurma tarafından veri toplama kontrol edebilirsiniz. Veri toplama denetimi, program yürütme, başlatma veya kapatma uygulamanın gibi belirli bir bölümü için veri toplamanıza olanak sağlar.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
1.  VSPerfCmd.exe seçenekleri aşağıdaki çiftleri başlatın ve veri toplama işlemini durdurun. Her komut satırı ayrı bir seçeneği belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) işlem kimliği tarafından belirtilen işlem için veri toplama (`PID`).|  
    |[/ attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ attach** işlem kimliği tarafından belirtilen işlem için veri toplamaya başlar (`PID`) veya işlem adı (ProcName). **/ detach** belirli bir işlemin belirtilmezse, tüm işlemler veya belirtilen işlem için veri toplamayı durdurur.|  
  
## <a name="ending-the-profiling-session"></a>Profil oluşturma oturumu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için Profil Oluşturucu veri toplamadığı gerekir. Profili uygulamayı kapatmak veya çağırma eşzamanlılık verileri toplama durdurabilirsiniz **VSPerfCmd / detach** seçeneği. Ardından çağırma **VSPerfCmd shutdown** profil oluşturucu devre dışı bırakma ve profil oluşturma veri dosyası kapatmak için seçeneği. **VSPerfClrEnv / kapalı** komutu profil ortam değişkenleri temizler.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Profil Oluşturucu hedef uygulamasından ayırmak için aşağıdakilerden birini yapın.  
  
    -   Hedef uygulamayı kapatın.  
  
         -veya-  
  
    -   Tür **VSPerfCmd / Ayır**  
  
2.  Profil Oluşturucu Kapat  
  
     **VSPerfCmd**[Shutdown](../profiling/shutdown.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık verileri toplama](../profiling/collecting-concurrency-data-for-stand-alone-applications.md)