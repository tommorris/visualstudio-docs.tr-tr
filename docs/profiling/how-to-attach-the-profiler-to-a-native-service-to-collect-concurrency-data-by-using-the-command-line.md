---
title: "Nasıl yapılır: komut satırını kullanarak eşzamanlılık verileri toplamak için bir yerel hizmete profil oluşturucu ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 283a1ee1-b43e-4daf-95ae-1311925a42a8
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 98cc07eaeac12a5d5b0e32279ddb30f0a888b5b9
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="how-to-attach-the-profiler-to-a-native-service-to-collect-concurrency-data-by-using-the-command-line"></a>Nasıl yapılır: Komut Satırını Kullanarak Eşzamanlılık Verileri Toplamak için Yerel bir Hizmete Profil Oluşturucu Ekleme
Bu konuda nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yerel (C/C++) için profil oluşturucu ekleme için profil oluşturma araçları komut satırı araçları örnekleme yöntemini kullanarak işlemi ve iş parçacığı eşzamanlılık verileri toplamak ve hizmeti.  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
> [!NOTE]
>  Profil Oluşturma Araçlarının komut satırı araçları, Visual Studio yükleme dizini altındaki \Team Tools\Performance Tools alt dizininde yer alır. 64-bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut isteminde kullanmak için Araçlar yolu PATH ortam değişkenine eklemeniz gerekir **komut istemi** penceresi veya komutu. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Hizmete profil oluşturucu eklenirken, duraklatma ve veri toplama sürdürme. Profil oluşturma oturumu sona erdirmek için profil oluşturucu artık hizmete bağlı olması gerekir ve profil oluşturucu açıkça kapatılmalıdır.  
  
## <a name="attaching-the-profiler"></a>Profil Oluşturucu ekleme  
 Bir yerel hizmete profil oluşturucu ekleme için kullandığınız **VSPerfCmd/başlangıç** ve **/ attach** profil oluşturucu başlatmak ve hedef uygulamaya eklemek için Seçenekler. Belirleyebileceğiniz **/start** ve **/ attach** ve bunlara karşılık gelen seçenekleri tek bir komut satırında. Ayrıca ekleyebileceğiniz **/globaloff** hedef uygulama başlangıcında veri toplamayı duraklatmak için seçeneği. Daha sonra **/globalon** veri toplamaya başlamak için.  
  
#### <a name="to-attach-the-profiler-to-a-native-service"></a>Bir yerel hizmete profil oluşturucu eklemek için  
  
1.  Hizmet çalışmıyorsa, hizmeti başlatın.  
  
2.  Profil oluşturucu komut isteminde aşağıdakini yazarak başlatın:  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency/Output:** `OutputFile` [`Options`]  
  
    -   [/Çıkış](../profiling/output.md)**:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile`ad ve profil oluşturma veri (.vsp) dosyasının konumunu belirtir.  
  
     Herhangi bir seçenek olan aşağıdaki tabloda kullanabileceğiniz **/start** seçeneği.  
  
    > [!NOTE]
    >  Çoğu hizmetlerinde **/user** ve **/crosssession** seçeneği.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain\`]`UserName`|Profil Oluşturucu için erişim verilecek hesabın kullanıcı adını ve isteğe bağlı etki alanını belirtir.|  
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturum açma oturumları işlemleri profil oluşturma.|  
    |[/wincounter](../profiling/wincounter.md) **:**`WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:**`Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500'dür.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:**`Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|  
  
3.  Bir komut isteminde aşağıdaki komutu yazarak hizmete profil oluşturucu ekleme:  
  
     **VSPerfCmd / ekleme:**`PID`  
  
     `PID`işlem kimliği veya işlem hedef uygulamanın adını belirtir. İşlem tüm çalışan işlemleri kimliklerini Windows Görev Yöneticisi'nde görüntüleyebilirsiniz.  
  
## <a name="controlling-data-collection"></a>Veri Toplama Denetimi  
 Hedef uygulama çalışırken, başlatma ve durdurma verileri VSPerfCmd.exe seçeneklerle dosyaya yazma tarafından veri toplama kontrol edebilirsiniz. Denetleme veri toplama işlemi tarafından program yürütme başlangıç veya uygulamayı kapatılıyor gibi belirli bir parçası için verileri toplayabilir.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Aşağıdaki tabloda seçeneklerinde çiftlerini başlatın ve veri toplama işlemini durdurun. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:**`PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) veri toplama işlemi için işlem kimliği (`PID`) belirtir.|  
    |[/ attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ attach** işlem için veri toplamaya başlar, işlem kimliği (`PID`) veya işlem adı (*ProcName*) belirtir. **/ detach** hiçbir işlem belirtilmişse, tüm işlemler veya belirtilen işlem için veri toplamayı durdurur.|  
  
## <a name="ending-the-profiling-session"></a>Profil oluşturma oturumu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için Profil Oluşturucu veri toplamadığı gerekir. Hizmetin durdurulması ya da çağırma eşzamanlılık yöntemiyle profili yerel bir hizmet veri toplamayı Durdur **VSPerfCmd / detach** seçeneği. Ardından çağırma **VSPerfCmd shutdown** profil oluşturucu devre dışı bırakma ve profil oluşturma veri dosyası kapatmak için seçeneği.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Profil Oluşturucu hedef uygulamasından hizmetin durdurulması veya bir komut isteminde aşağıdaki komutu yazarak bağlantısını kesin:  
  
     Tür **VSPerfCmd / Ayır**  
  
2.  Profil oluşturucu komut isteminde aşağıdaki komutu yazarak kapatın:  
  
     **VSPerfCmd**[Shutdown  ](../profiling/shutdown.md)