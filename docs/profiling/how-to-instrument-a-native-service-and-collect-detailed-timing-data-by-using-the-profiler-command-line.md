---
title: 'Nasıl yapılır: Profil oluşturucu komut satırını kullanarak izleme yerel hizmet ve ayrıntılı zamanlama verileri toplama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: dfe58b39-63f8-4a87-ab3a-2b5b14faa8d0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 9dcd4052078a3a7327b0a48fca8812a2d5393917
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-instrument-a-native-service-and-collect-detailed-timing-data-by-using-the-profiler-command-line"></a>Nasıl yapılır: Profil Oluşturucu Komut Satırını Kullanarak Yerel bir Hizmeti İzleme ve Ayrıntılı Zamanlama Verileri Toplama
Bu konuda nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yerel (C/C++) işaretlemesini profil oluşturma araçları komut satırı araçları hizmet ve ayrıntılı zamanlama verileri toplama.  
  
> [!NOTE]
>  Bilgisayar başlatıldıktan sonra hizmeti yeniden başlatılamıyor, bir hizmeti izleme yöntemiyle profil olamaz, yalnızca işletim sistemi başladığında, bu tür bir hizmet başlatın.  
>   
>  Profil oluşturma araçları komut satırı araçları \Team Tools\Performance araçları alt dizininde bulunan [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64 bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 İzleme metodunu kullanarak bir yerel hizmetinden ayrıntılı zamanlama verileri toplamak için kullandığınız [VSInstr.exe](../profiling/vsinstr.md) bileşenin izleme eklenmiş bir sürümünü oluşturmak için aracı. Ardından hizmetinin izlenmiş olmayan sürümü Araçlı sürümüyle hizmeti el ile başlatmak için yapılandırıldığından emin yapmadan değiştirin. Ardından, profil oluşturucu de başlatın.  
  
 Hizmet başlatıldığında, zamanlama verileri bir veri dosyası otomatik olarak toplanır. Duraklatma ve veri toplama sırasında profil oluşturma oturumu sürdürün.  
  
 Profil oluşturma oturumu sonlandırmak için hizmetini kapatmak ve profil oluşturucu açıkça kapatın.  
  
## <a name="starting-the-application-with-the-profiler"></a>Profil Oluşturucu ile uygulama başlatma  
  
#### <a name="to-start-profiling-a-native-service"></a>Bir yerel hizmete profil oluşturmayı başlatmak için  
  
1.  Bir komut istemi penceresi açın.  
  
2.  Kullanım **Vsınstr** hizmeti ikili Araçlı bir sürümünü oluşturmak için aracı.  
  
3.  Özgün ikili Araçlı sürümle değiştirin. Windows Hizmet Denetimi Yöneticisi'nde, hizmet başlatma türünü manuel olarak ayarlandığından emin olun.  
  
4.  Profil Oluşturucu başlatın. Tür:  
  
     **VSPerfCmd** [/start](../profiling/start.md) **: izleme**[/çıkış](../profiling/output.md) **:** `OutputFile` [`Options`]    
  
    -   **/Start:trace** seçeneği profil oluşturucu başlatır.  
  
    -   **/Çıktı:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile` Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     İle aşağıdaki seçeneklerden birini kullanabilirsiniz **/start:trace** seçeneği.  
  
    > [!NOTE]
    >  **/User** ve **/crosssession** seçenekleri ASP.NET uygulamaları için genellikle gerekli.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|ASP.NET çalışan işlemin sahibi olan hesabın etki alanı ve kullanıcı adını belirtir. İşlem oturum açan kullanıcının başka bir kullanıcı olarak çalışıyorsa, bu seçeneği gereklidir. İşlem sahibi, Windows Görev Yöneticisi'nin İşlemler sekmesinde kullanıcı adı sütununda listelenir.|  
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturum açma oturumları işlemleri profil oluşturma. ASP.NET uygulamasını farklı bir oturumda çalışıyorsa, bu seçeneği gereklidir. Oturum kimliği, Windows Görev Yöneticisi'nin İşlemler sekmesinde oturum kimliği sütununda listelenir. **/CS** için bir kısaltma olarak belirtilen **/crosssession**.|  
    |[/waitstart](../profiling/waitstart.md)[**:**`Interval`]|Bir hata döndürmeden önce başlatmak profil oluşturucu için beklenecek saniye sayısını belirtir. Varsa `Interval` belirtilmezse, profil oluşturucu sonsuza kadar bekler. Varsayılan olarak, **/start** hemen döndürür.|  
    |[/globaloff](../profiling/globalon-and-globaloff.md)|Profil Oluşturucu ile veri toplama başlatmak için duraklatıldı, ekleme **/globaloff** için seçenek **/start** komut satırı. Kullanım **/globalon** profil sürdürmek için.|  
    |[/ sayacı](../profiling/counter.md) **:** `Config`|İşlemci performansı sayaç yapılandırma dosyasında belirtilen bilgi toplar. Sayaç bilgileri her profil olay, toplanan veriler eklenir.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|  
  
5.  Hizmeti Hizmet Denetim Yöneticisi'nden başlatın.  
  
## <a name="controlling-data-collection"></a>Veri Toplama Denetimi  
 Hizmet çalışırken kullanabileceğiniz **VSPerfCmd.exe** Profil Oluşturucu veri dosyası için veri yazma durdurmak ve başlatmak için Seçenekler. Veri toplama denetimi, program yürütme, başlatılıyor veya hizmeti kapatılıyor gibi belirli bir bölümü için veri toplamanıza olanak sağlar.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Aşağıdaki çiftleri **VSPerfCmd** seçenekleri başlatma ve durdurma veri toplama. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) işlem kimliği tarafından belirtilen işlem için veri toplama (`PID`).|  
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:** `TID`|Başlatır (**/threadon**) veya durdurulduğunda (**/threadoff**) Kimlikli iş parçacığı tarafından belirtilen iş parçacığı için veri toplama (`TID`).|  
  
## <a name="ending-the-profiling-session"></a>Profil oluşturma oturumu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için izleme eklenmiş bileşenini çalıştıran hizmetini durdurun ve ardından çağıran **VSPerfCmd**[shutdown](../profiling/shutdown.md) profil oluşturucu kapatmak ve profil oluşturma veri dosyası kapatmak için seçeneği.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Hizmet Denetimi Yöneticisi'nden hizmetini durdurun.  
  
2.  Profil Oluşturucu kapatın. Tür:  
  
     **VSPerfCmd Shutdown**  
  
3.  İzleme eklenmiş modülü özgün ile değiştirin. Gerekirse, hizmet başlangıç türünü yeniden yapılandırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)   
 [İzleme Metodu Veri Görünümleri](../profiling/instrumentation-method-data-views.md)