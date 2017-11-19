---
title: "Nasıl yapılır: statik olarak derlenmiş bir ASP.NET Web uygulamasını izleme profil oluşturucu komut satırını kullanarak uygulama ve bellek verileri toplama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea1dcb7c-1dc3-49ff-9418-8795b5b3d3bc
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 30ad7561ffadb4c8d139c7be8dc537dc8f1f092b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-instrument-a-statically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line"></a>Nasıl yapılır: Profil Oluşturucu Komut Satırını Kullanarak Statik Olarak Derlenmiş bir ASP.NET Web Uygulamasını İzleme ve Bellek Verileri Toplama
Bu konuda nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] önceden derlenmiş işaretlemesini profil oluşturma araçları komut satırı araçları [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web bileşeni veya Web sitesi, ayrıntılı zamanlama verileri ve toplama .NET bellek ayırma ve nesne yaşam süresi.  
  
> [!NOTE]
>  Profil oluşturma araçları komut satırı araçları \Team Tools\Performance araçları alt dizininde bulunan [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64 bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Verileri toplamak için bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] izleme metodunu kullanarak Web bileşeni kullandığınız [VSInstr.exe](../profiling/vsinstr.md) bileşenin izleme eklenmiş bir sürümünü oluşturmak için aracı. Bileşeni barındıran bilgisayarda bileşen izlenmiş olmayan sürümü Araçlı sürümle değiştirin. Daha sonra [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) genel profil ortam değişkenlerini başlatmak ve ana bilgisayarı yeniden başlatmak için araç. Ardından, profil oluşturucu de başlatın.  
  
 İzleme eklenmiş bileşen yürütüldüğünde, zamanlama verileri bir veri dosyası otomatik olarak toplanır. Duraklatma ve veri toplama sırasında profil oluşturma oturumu sürdürün.  
  
 Profil oluşturma oturumu sona erdirmek için kapatmak [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] bileşeni barındıran ve profil oluşturucu açıkça Kapat çalışan işlemi. Çoğu durumda, bir oturumun sonunda profil ortam değişkenleri temizleme öneririz.  
  
## <a name="starting-to-profile"></a>Profile başlatılıyor  
  
#### <a name="to-instrument-an-aspnet-web-component-and-start-profiling"></a>Bir ASP.NET Web bileşenini izleme ve profil oluşturmayı başlatmak için  
  
1.  Kullanım **Vsınstr** hedef uygulama izleme eklenmiş bir sürümünü oluşturmak için aracı. Gerekirse, uygulama ikili dosyaları ASP.NET ana bilgisayarda izleme eklenmiş ikili dosyalar ile değiştirin.  
  
2.  Bir komut istemi penceresi açın  
  
3.  Ortam değişkenleri profil .NET başlatır. Bir komut istemi penceresinde yazın:  
  
     **VSPerfClrEnv /globaltracegc**  
  
     veya  
  
     **VSPerfClrEnv /globaltracegclife**  
  
    -   **/globaltracegc** .NET bellek ayırma ve zamanlama verileri toplar.  
  
    -   **/globaltracegclife** toplar .NET bellek ayırma, nesne yaşam süresi ve ayrıntılı zamanlama verileri.  
  
4.  Bilgisayarı yeniden başlatın.  
  
5.  Bir komut istemi penceresi açın.  
  
6.  Profil Oluşturucu başlatın. Bir komut istemi penceresinde yazın:  
  
     **VSPerfCmd /start:trace/Output:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md)**: izleme** seçeneği profil oluşturucu başlatır.  
  
    -   [/Çıkış](../profiling/output.md)**:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile`Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     İle aşağıdaki seçeneklerden birini kullanabilirsiniz **/start:trace** seçeneği.  
  
    > [!NOTE]
    >  **/User** ve **/crosssession** seçenekleri ASP.NET uygulamaları için genellikle gerekli.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|ASP.NET çalışan işlemin sahibi olan hesabın kullanıcı adını ve isteğe bağlı etki alanını belirtir. İşlem oturum açan kullanıcının farklı bir kullanıcı olarak çalışıyorsa, bu seçeneği gereklidir. Adı, Windows Görev Yöneticisi'nin İşlemler sekmesinde kullanıcı adı sütununda listelenir.|  
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturumlarda işlemleri profil oluşturma. Bu seçenek, uygulamanın farklı bir oturumda çalışıyorsa gereklidir. Oturum kimliği, Windows Görev Yöneticisi'nin İşlemler sekmesinde oturum kimliği sütununda listelenir. **/CS** için bir kısaltma olarak belirtilen **/crosssession**.|  
    |[/wincounter](../profiling/wincounter.md) **:**`WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:**`Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:**`Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|  
    |[/globaloff](../profiling/globalon-and-globaloff.md)|Profil Oluşturucu ile veri toplama başlatmak için duraklatıldı, ekleme **/globaloff** için seçenek **/start** komut satırı. Kullanım **/globalon** profil sürdürmek için.|  
  
7.  İzleme eklenmiş bileşen içeren Web sitesini açın.  
  
## <a name="controlling-data-collection"></a>Veri Toplama Denetimi  
 Hedef uygulama çalışırken, başlatma ve kullanarak verileri dosyaya yazma durdurma tarafından veri toplama denetleyebilirsiniz **VSPerfCmd.exe** seçenekleri. Veri toplama denetimi, program yürütme, başlatılıyor veya uygulama kapatılmadan gibi belirli bir bölümü için veri toplamanıza olanak sağlar.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Seçenekler aşağıdaki çiftleri başlatın ve veri toplama işlemini durdurun. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:**`PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) işlem kimliği tarafından belirtilen işlem için veri toplama (`PID`).|  
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:**`TID`|Başlatır (**/threadon**) veya durdurulduğunda (**/threadoff**) Kimlikli iş parçacığı tarafından belirtilen iş parçacığı için veri toplama (`TID`).|  
  
## <a name="ending-the-profiling-session"></a>Profil oluşturma oturumu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için kapatmak [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması ve Internet Information Services (IIS) kullanan **IISReset** kapatmak için komut [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] çalışan işlemi. Çağrı **VSPerfCmd** [shutdown](../profiling/shutdown.md) profil oluşturucu kapatmak ve profil oluşturma veri dosyası kapatmak için seçeneği. **VSPerfClrEnv /globaloff** komutu profil ortam değişkenleri temizler. Yeni ortam ayarlarının uygulanması için bilgisayarı yeniden başlatmanız gerekir.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Kapat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması.  
  
2.  Kapat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] çalışan işlemi. Tür:  
  
     **IISReset/stop**  
  
3.  Profil Oluşturucu kapatın. Tür:  
  
     **VSPerfCmd Shutdown**  
  
4.  (İsteğe bağlı). Profil oluşturma ortam değişkenleri temizleyin. Tür:  
  
     **VSPerfCmd /globaloff**  
  
5.  Bilgisayarı yeniden başlatın. Gerekirse, IIS'yi yeniden başlatın. Tür:  
  
     **IISReset/Start**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [.NET bellek verisi görünümleri](../profiling/dotnet-memory-data-views.md)