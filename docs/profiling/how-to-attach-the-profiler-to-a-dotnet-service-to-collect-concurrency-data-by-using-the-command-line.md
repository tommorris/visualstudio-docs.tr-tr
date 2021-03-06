---
title: 'Nasıl yapılır: komut satırını kullanarak eşzamanlılık verileri toplamak için bir .NET hizmetine profil oluşturucu ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: ffbdfe37-8325-44be-bd36-2c8aab2dec7b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 60f300f58c0cc9c06d8af64a4054b95306899f3a
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815749"
---
# <a name="how-to-attach-the-profiler-to-a-net-service-to-collect-concurrency-data-by-using-the-command-line"></a>Nasıl yapılır: komut satırını kullanarak eşzamanlılık verileri toplamak için bir .NET hizmetine profil oluşturucu ekleme
Bu makalede nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] için profil oluşturucu ekleme için profil oluşturma araçları komut satırı araçları bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] hizmet ve örnekleme yöntemini kullanarak işlemi ve iş parçacığı eşzamanlılık verileri toplama.  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
> [!NOTE]
>  Profil oluşturma araçları komut satırı araçları içinde bulunur *\Team Tools\Performance Araçları* Visual Studio yükleme dizininin alt. 64-bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Eşzamanlılık verileri toplamak için profil oluşturucu hizmet işlemini ekleme. Hizmete profil oluşturucu eklenirken, duraklatma ve veri toplama sürdürme. Profil oluşturma oturumu sona erdirmek için profil oluşturucu artık hizmete bağlı olması gerekir ve profil oluşturucu açıkça kapatılmalıdır. Çoğu durumda, bir oturumun sonunda profil ortam değişkenleri temizleme öneririz.  
  
## <a name="attach-the-profiler"></a>Profil Oluşturucu ekleme  
  
#### <a name="to-attach-the-profiler-to-a-net-framework-service"></a>Profil oluşturucuyu bir .NET Framework hizmetine eklemek için  
  
1.  Hizmetini yükleyin.  
  
2.  Bir komut penceresi açın.  
  
3.  Profil oluşturma ortam değişkenleri başlatır. Tür:  
  
     [VSPerfClrEnv](../profiling/vsperfclrenv.md) **/globalsampleon** [**/samplelineoff**]  
  
    -   **/globalsampleon** örnekleme sağlar.  
  
    -   **/samplelineoff** belirli bir kaynak kod satırı için toplanan verileri atama devre dışı bırakır. Bu seçenek belirtildiğinde, verileri yalnızca işlevleriyle atanır.  
  
4.  Bilgisayarı yeniden başlatın.  
  
5.  Profil Oluşturucu başlatın. Tür:  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency/Output:** `OutputFile` [`Options`]  
  
     [/Çıkış](../profiling/output.md)**:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile` Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     İle aşağıdaki seçeneklerden birini kullanabilirsiniz **/start** seçeneği.  
  
    > [!NOTE]
    >  **/User** ve **/crosssession** seçenekleri hizmetler için genellikle gerekli.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Profili işleme sahip hesabın etki alanı ve kullanıcı adını belirtir. Bu seçenek, yalnızca işlem oturum açan kullanıcının başka bir kullanıcı olarak çalışıyorsa gereklidir. İşlem sahibi listelenen **kullanıcı adı** sütunu **işlemleri** sekmesi Windows Görev Yöneticisi'nin.|  
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturumlarda işlemleri profil oluşturma. Farklı bir oturumda Hizmeti çalışıyorsa, bu seçeneği gereklidir. Oturum kimliği listelenir **oturum kimliği** sütunu **işlemleri** sekmesi Windows Görev Yöneticisi'nin. **/CS** için bir kısaltma olarak belirtilen **/crosssession**.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı bir toplanır (. *etl*) dosyası.|  
  
6.  Gerekirse, hizmeti başlatın.  
  
7.  Hizmete profil oluşturucu ekleme. Tür:  
  
     **VSPerfCmd / ekleme:** `PID` [[/targetclr](../profiling/targetclr.md)**:**`Version`]  
  
    -   `PID` işlem kimliği veya hizmetin işlem adı belirtir. İşlem tüm çalışan işlemleri kimliklerini Windows Görev Yöneticisi'nde görüntüleyebilirsiniz.  
  
    -   **targetclr:** `Version` bir uygulamada birden fazla çalışma zamanı sürümü yüklendiğinde profiline ortak dil çalışma zamanı (CLR) sürümünü belirtir. İsteğe bağlı.  
  
## <a name="control-data-collection"></a>Veri toplamayı denetleme  
 Hizmet çalışırken, başlatma ve kullanarak verileri dosyaya yazma durdurma tarafından veri toplama denetleyebilirsiniz *VSPerfCmd.exe* seçenekleri. Veri toplama denetimi, program yürütme, başlatma veya kapatma uygulamanın gibi belirli bir bölümü için veri toplamanıza olanak sağlar.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Aşağıdaki çiftleri **VSPerfCmd** seçenekleri başlatma ve durdurma veri toplama. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) işlem kimliği tarafından belirtilen işlem için veri toplama (`PID`).|  
    |**/ ekleme:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[: {`PID`&#124;`ProcName`}]|**/ attach** işlem kimliği veya işlem adı tarafından belirtilen işlem için veri toplamaya başlar. **/ detach** belirli bir işlemin belirtilmezse, tüm işlemler veya belirtilen işlem için veri toplamayı durdurur.|  
  
-   Aynı zamanda **VSPerfCmd.exe**[/işaretlemek](../profiling/mark.md) profil işareti veri dosyasına eklemek için seçeneği. **/İşaretlemek** komut tanımlayıcı, bir zaman damgası ve bir kullanıcı tanımlı isteğe bağlı bir metin dizesi ekler. İşaretleri Profil Oluşturucusu rapor ve veri görünümleri verilerini filtrelemek için kullanılabilir. VSPerfCmd seçenekleri aşağıdaki çiftleri başlatın ve veri toplama işlemini durdurun. Her komut satırı ayrı bir seçeneği belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
## <a name="end-the-profiling-session"></a>Profil oluşturma oturumunu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için Profil Oluşturucu veri toplamadığı gerekir. Hizmetin durdurulması ya da çağırma eşzamanlılık yöntemiyle profili bir uygulamadan veri toplamayı Durdur **VSPerfCmd / detach** seçeneği. Ardından çağırma **VSPerfCmd shutdown** profil oluşturucu kapatmak ve profil oluşturma veri dosyası kapatmak için seçeneği. **VSPerfClrEnv /globaloff** komutu temizler profil ortam değişkenleri, ancak bilgisayar yeniden başlatılana kadar sistem yapılandırması sıfırlanmaz.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Profil Oluşturucu hedef uygulamasından ayırmak için aşağıdakilerden birini yapın.  
  
    -   Hizmetini durdurun.  
  
         veya  
  
    -   Tür **VSPerfCmd / ayırın.**  
  
2.  Profil Oluşturucu kapatın. Tür:  
  
     **VSPerfCmd**[kapatma](../profiling/shutdown.md)
