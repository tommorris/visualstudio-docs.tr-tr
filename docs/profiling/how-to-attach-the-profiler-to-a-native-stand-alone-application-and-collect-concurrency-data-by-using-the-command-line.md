---
title: 'Nasıl yapılır: Profil oluşturucu komut satırını kullanarak bir yerel tek başına uygulama ve eşzamanlılık verileri toplama için ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 12d3e0f3-4b74-4e66-8fbf-8ac99bd4f91c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 6c12b2d0a2a3851e825620345524a4786dcd0c44
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-attach-the-profiler-to-a-native-stand-alone-application-and-collect-concurrency-data-by-using-the-command-line"></a>Nasıl yapılır: Profil Oluşturucu Komut Satırını Kullanarak Yerel bir Bağımsız Uygulamaya Profil Oluşturucu Ekleme ve Eşzamanlılık Verileri Toplama
Bu konuda nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çalışan yerel bir (C/C++) bağımsız uygulamaya profil oluşturucu ekleme ve toplamak için profil oluşturma araçları komut satırı araçları iş parçacığı çakışma verileri.  
  
> [!NOTE]
>  Profil Oluşturma Araçlarının komut satırı araçları, Visual Studio yükleme dizini altındaki \Team Tools\Performance Tools alt dizininde yer alır. 64-bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçları kullanmak için PATH ortam değişkenine araçları yolu eklemelisiniz **komut istemi** penceresi veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Profil Oluşturucu uygulamaya bağlı olsa da, duraklatma ve veri toplama sürdürme. Profil oluşturma oturumu sona erdirmek için profil oluşturucu artık uygulamaya bağlı olması gerekir ve profil oluşturucu açıkça kapatılmalıdır.  
  
## <a name="attaching-the-profiler-to-a-running-native-application"></a>Çalışan yerel bir uygulamaya profil oluşturucu ekleme  
  
#### <a name="to-attach-the-profiler-to-a-running-native-application"></a>Profil Oluşturucu çalışan yerel bir uygulamaya eklemek için  
  
1.  Bir komut isteminde aşağıdaki komutu yazın:  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency**  
  
     Aşağıdaki tablo ile seçeneklerinden herhangi birini kullanabilirsiniz **/start:concurrency**seçeneği.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain\`]`Username`|Profil Oluşturucu için erişim verilecek hesabın kullanıcı adını ve isteğe bağlı etki alanını belirtir.|  
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturum açma oturumları işlemleri profil oluşturma.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500'dür.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|  
  
2.  Aşağıdaki komutu yazarak hedef uygulamaya profil oluşturucu ekleme:  
  
     **VSPerfCmd**[/ attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`}    
  
     `PID` Hedef uygulama işlem Kimliğini belirtir. İşlem tüm çalışan işlemleri kimliklerini Windows Görev Yöneticisi'nde görüntüleyebilirsiniz.  
  
## <a name="controlling-data-collection"></a>Veri Toplama Denetimi  
 Hedef uygulama çalışırken, başlatma ve VSPerfCmd.exe seçenekleri kullanarak verileri dosyaya yazma durdurma tarafından veri toplama kontrol edebilirsiniz. Denetleme veri toplama işlemi tarafından program yürütme başlangıç veya uygulamayı kapatılıyor gibi belirli bir parçası için verileri toplayabilir.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Aşağıdaki tabloda seçeneklerinde çiftlerini başlatın ve veri toplama işlemini durdurun. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) veri toplama işlemi için işlem kimliği (`PID`) belirtir.|  
    |[/ attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ attach** işlem için veri toplamaya başlar, işlem kimliği (`PID`) veya işlem adı (*ProcName*) belirtir. **/ detach** hiçbir işlem belirtilmişse, tüm işlemler veya belirtilen işlem için veri toplamayı durdurur.|  
  
## <a name="ending-the-profiling-session"></a>Profil oluşturma oturumu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için Profil Oluşturucu veri toplamadığı gerekir. Örnekleme yöntemi ile uygulama kapatarak ya da çağırma profili bir uygulamadan veri toplamayı Durdur **VSPerfCmd / detach** seçeneği. Ardından çağırma **VSPerfCmd shutdown** profil oluşturucu kapatmak ve profil oluşturma veri dosyası kapatmak için seçeneği.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Profil Oluşturucu hedef uygulamasından kapatma veya aşağıdaki komutu yazarak bağlantısını kesin:  
  
     **VSPerfCmd / Ayır**  
  
2.  Profil Oluşturucu, aşağıdaki komutu yazarak kapatın:  
  
     **VSPerfCmd**[Shutdown](../profiling/shutdown.md)