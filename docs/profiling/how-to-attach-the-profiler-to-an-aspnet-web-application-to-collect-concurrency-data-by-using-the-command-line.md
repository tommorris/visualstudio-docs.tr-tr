---
title: 'Nasıl yapılır: komut satırını kullanarak eşzamanlılık verileri toplamak için bir ASP.NET Web uygulamasına profil oluşturucu ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 0e215fdd-55f8-43ef-9534-06542eefe223
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 09ba7884d9c8bd1abf9762046b9e8f7fb534d530
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766015"
---
# <a name="how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-concurrency-data-by-using-the-command-line"></a>Nasıl yapılır: komut satırını kullanarak eşzamanlılık verileri toplamak için bir ASP.NET web uygulamasına profil oluşturucu ekleme
Bu makalede nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir ASP.NET uygulamasına profil oluşturucu ekleme ve işlem ve iş parçacığı eşzamanlılık verileri toplamak için profil oluşturma araçları komut satırı araçları.  
  
 Profil oluşturma araçları komut satırı araçları içinde bulunur *\Team Tools\Performance Araçları* Visual Studio yükleme dizininin alt. 64-bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut isteminde kullanmak için Araçlar yolu PATH ortam değişkenine eklemeniz gerekir **komut istemi** penceresi veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Eşzamanlılık verileri toplamak için Web sitenizi barındıran ASP.NET çalışan işlemi için profil oluşturucu ekleme. Profil Oluşturucu uygulamaya bağlı olsa da, duraklatma ve veri toplama sürdürme. Profil oluşturma oturumu sona erdirmek için profil oluşturucu artık uygulamaya bağlı olması gerekir ve profil oluşturucu açıkça kapatılmalıdır. Çoğu durumda, bir oturumun sonunda profil ortam değişkenleri temizlemeniz gerekir.  
  
## <a name="attach-the-profiler"></a>Profil Oluşturucu ekleme  
  
#### <a name="to-attach-the-profiler-to-a-aspnet-application"></a>Bir ASP.NET uygulamasına profil oluşturucu ekleme için  
  
1.  Profil Oluşturucu, aşağıdaki komutu yazarak başlatın:  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency/Output:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md) seçeneği kaynak çakışması veri toplamak için profil oluşturucu başlatır.  
  
    -   [/Çıkış](../profiling/output.md)**:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile` Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     Herhangi bir seçenek olan aşağıdaki tabloda kullanabileceğiniz **/start** seçeneği.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain\`]`UserName`|Profil Oluşturucu için erişim verilecek hesabın kullanıcı adını ve isteğe bağlı etki alanını belirtir.|  
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturum açma oturumları işlemleri profil oluşturma.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500'dür.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı bir toplanır (. *etl*) dosyası.|  
  
2.  ASP.NET uygulaması normal şekilde başlatın.  
  
3.  Aşağıdaki komutu yazarak ASP.NET çalışan işlemi için profil oluşturucu ekleme:**VSPerfCmd / ekleme:** `PID` [**/targetclr:**`Version`]  
  
    -   `PID` Kimliği veya ASP.NET çalışan işlemin adını belirtir. İşlem tüm çalışan işlemleri kimliklerini Windows Görev Yöneticisi'nde görüntüleyebilirsiniz.  
  
    -   [/targetclr](../profiling/targetclr.md) **:** `Version` bir uygulamada birden fazla çalışma zamanı sürümü yüklendiğinde profiline ortak dil çalışma zamanı (CLR) sürümünü belirtir. Bu parametre isteğe bağlıdır.  
  
## <a name="control-data-collection"></a>Veri toplamayı denetleme  
 Uygulama çalışırken, başlatma ve kullanarak verileri dosyaya yazma durdurma tarafından veri toplama denetleyebilirsiniz *VSPerfCmd.exe* seçenekleri. Denetleme veri toplama işlemi tarafından program yürütme başlangıç veya uygulamayı kapatılıyor gibi belirli bir parçası için verileri toplayabilir.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   VSPerfCmd seçenekleri aşağıdaki tabloda çiftlerini başlatın ve veri toplama işlemini durdurun. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) veri toplama işlemi için işlem kimliği (`PID`) belirtir.|  
    |[/ attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ attach** işlem için veri toplamaya başlar, işlem kimliği (`PID`) veya işlem adı (*ProcName*) belirtir. **/ detach** hiçbir işlem belirtilmişse, tüm işlemler veya belirtilen işlem için veri toplamayı durdurur.|  
  
## <a name="end-the-profiling-session"></a>Profil oluşturma oturumunu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için Profil Oluşturucu veri toplamadığı gerekir. Eşzamanlılık yöntemi ile ASP.NET çalışan işlemi başlatarak veya çağırma profili bir uygulamadan veri toplamayı Durdur **VSPerfCmd / detach** seçeneği. Ardından çağırma **VSPerfCmd shutdown** profil oluşturucu devre dışı bırakma ve profil oluşturma veri dosyası kapatmak için seçeneği. **VSPerfClrEnv /globaloff** komutu temizler profil ortam değişkenleri, ancak bilgisayar yeniden başlatılana kadar sistem yapılandırması sıfırlanmaz.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Profil Oluşturucu hedef uygulamasından kapatma veya bir komut isteminde aşağıdakileri yazarak bağlantısını kesin:  
  
     **VSPerfCmd / Ayır**  
  
2.  Profil oluşturucu komut isteminde aşağıdaki komutu yazarak kapatın:  
  
     **VSPerfCmd**[Shutdown](../profiling/shutdown.md)  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Profil ASP.NET web uygulamaları](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma VSPerfASPNETCmd ile hızlı web sitesi](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)