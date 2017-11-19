---
title: "Nasıl yapılır: komut satırını kullanarak eşzamanlılık verileri toplamak için bağımsız bir yerel uygulamayı Profil Oluşturucu ile başlatma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5aed651-afed-4b70-9a7e-1a6032cc614f
caps.latest.revision: "23"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 625bc1301d4ea4a43fdd3dec7f28eb26171eb503
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-launch-a-stand-alone-native-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line"></a>Nasıl yapılır: Komut Satırını Kullanarak Eşzamanlılık Verileri Toplamak için Bağımsız bir Yerel Uygulamayı Başlatma
Bu konuda nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yerel tek başına (istemci) uygulaması başlatmak ve işlem ve iş parçacığı eşzamanlılık verileri toplamak için profil oluşturma araçları komut satırı araçları.  
  
 Profil oluşturma oturumu aşağıdaki bölümleri içerir:  
  
-   Profil Oluşturucu ile uygulama başlatma  
  
-   Veri toplama denetimi  
  
-   Profil oluşturma oturumu sona erdirme  
  
> [!NOTE]
>  Profil oluşturma araçları komut satırı araçları \Team Tools\Performance araçları alt dizininde bulunan [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64-bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut isteminde kullanmak için Araçlar yolu PATH ortam değişkenine eklemeniz gerekir **komut istemi** penceresi veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
## <a name="starting-the-application-with-the-profiler"></a>Profil Oluşturucu ile uygulama başlatma  
 Profil Oluşturucu ile bir hedef uygulamayı başlatmak için kullandığınız [VSPerfCmd.exe](../profiling/vsperfcmd.md)**/start** ve **/başlatma** profil oluşturucu başlatın ve uygulamayı başlatmak için Seçenekler. Belirleyebileceğiniz **/start** ve **/başlatma** ve bunlara karşılık gelen seçenekleri. Ayrıca ekleyebileceğiniz **/globaloff** hedef uygulama başlangıcında veri toplamayı duraklatmak için seçeneği. Daha sonra **/globalon** veri toplamaya başlamak için.  
  
#### <a name="to-start-an-application-with-the-profiler"></a>Profil Oluşturucu ile bir uygulamayı başlatmak için  
  
1.  Bir komut isteminde aşağıdaki komutu yazın:  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency/Output:** `OutputFile` [`Options`]  
  
     [/Çıkış](../profiling/output.md)**:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile`Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     Aşağıdaki tablo ile seçeneklerinden herhangi birini kullanabilirsiniz **/start:concurrency** seçeneği.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/wincounter](../profiling/wincounter.md) **:**`WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:**`Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500'dür.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:**`Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|  
  
2.  Hedef uygulama yazarak başlatın:  
  
     **VSPerfCmd**[/başlatma](../profiling/launch.md) **:** `AppName` [`Options`]    
  
     Aşağıdaki tablo ile seçeneklerinden herhangi birini kullanabilirsiniz **/başlatma** seçeneği.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/args](../profiling/args.md) **:**`Arguments`|Hedef uygulamaya geçirilecek komut satırı bağımsız değişkenleri içeren bir dize belirtir.|  
    |[/ Console](../profiling/console.md)|Hedef komut satırı uygulaması ayrı bir pencerede başlatır.|  
    |[/targetclr](../profiling/targetclr.md) **:**`CLRVersion`|Ortak dil çalışma zamanı (CLR) uygulama CLR birden fazla sürümünü yüklerse profilini sürümünü belirtir.|  
  
## <a name="controlling-data-collection"></a>Veri Toplama Denetimi  
 Hedef uygulama çalışırken, başlatma ve durdurma verileri VSPerfCmd.exe seçeneklerle dosyaya yazma tarafından veri toplama kontrol edebilirsiniz. Denetleme veri toplama işlemi tarafından program yürütme başlangıç veya uygulamayı kapatılıyor gibi belirli bir parçası için verileri toplayabilir.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Aşağıdaki tabloda seçeneklerinde çiftlerini başlatın ve veri toplama işlemini durdurun. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:**`PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) veri toplama işlemi için işlem kimliği (`PID`) belirtir.|  
    |[/ attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ attach** işlem için veri toplamaya başlar, işlem kimliği (`PID`) veya işlem adı (*ProcName*) belirtir. **/ detach** hiçbir işlem belirtilmişse, tüm işlemler veya belirtilen işlem için veri toplamayı durdurur.|  
  
-   Aynı zamanda **VSPerfCmd.exe**[/işaretlemek](../profiling/mark.md) profil işareti veri dosyasına eklemek için seçeneği. **/İşaretlemek** komut tanımlayıcı, bir zaman damgası ve bir kullanıcı tanımlı isteğe bağlı bir metin dizesi ekler. İşaretleri Profil Oluşturucusu rapor ve veri görünümleri verilerini filtrelemek için kullanılabilir.  
  
## <a name="ending-the-profiling-session"></a>Profil oluşturma oturumu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için Profil Oluşturucu veri toplamadığı gerekir. Profili uygulamayı kapatmak veya çağırma eşzamanlılık verileri toplama durdurabilirsiniz **VSPerfCmd / detach** seçeneği. Ardından çağırma **VSPerfCmd shutdown** profil oluşturucu devre dışı bırakma ve profil oluşturma veri dosyası kapatmak için seçeneği.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Profil Oluşturucu hedef uygulamasından kapatma veya bir komut isteminde aşağıdaki komutu yazarak bağlantısını kesin:  
  
     **VSPerfCmd / Ayır**  
  
2.  Profil oluşturucu komut isteminde aşağıdaki komutu yazarak kapatın:  
  
     **VSPerfCmd**[Shutdown  ](../profiling/shutdown.md)