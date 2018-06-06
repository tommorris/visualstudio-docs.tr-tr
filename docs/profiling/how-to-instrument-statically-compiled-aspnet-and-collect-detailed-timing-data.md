---
title: 'Nasıl yapılır: statik olarak derlenmiş bir ASP.NET Web uygulamasını izleme ve ayrıntılı zamanlama verileri Profil Oluşturucu ile komut satırını kullanarak toplama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: b260ce68-76e6-4c3b-8062-3c00bd5cf7b8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 111839b6e50f9c0f3df7171683d2d6b4361c3611
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34814706"
---
# <a name="how-to-instrument-a-statically-compiled-aspnet-web-application-and-collect-detailed-timing-data-with-the-profiler-by-using-the-command-line"></a>Nasıl yapılır: statik olarak derlenmiş bir ASP.NET web uygulamasını izleme ve komut satırını kullanarak profil oluşturucu ile ayrıntılı zamanlama verileri toplama
Bu makalede nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları komut satırı araçları bir önceden derlenmiş işaretlemesini [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] web bileşeni veya web sitesi ve ayrıntılı zamanlama verileri toplama.  
  
> [!NOTE]
>  Profil oluşturma araçları komut satırı araçları içinde bulunur *\Team Tools\Performance Araçları* alt [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64-bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
>   
>  Profil oluşturma çalışmaya katman etkileşim verileri ekleme belirli yordamları profil oluşturma araçları komut satırıyla gerektirir. Bkz: [katman etkileşim verileri toplama](../profiling/adding-tier-interaction-data-from-the-command-line.md).  
  
 Ayrıntılı zamanlama verileri toplamak için bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] izleme metodunu kullanarak Web bileşeni kullandığınız [VSInstr.exe](../profiling/vsinstr.md) bileşenin izleme eklenmiş bir sürümünü oluşturmak için aracı. Bileşeni barındıran bilgisayarda bileşenin noninstrumented sürümünü Araçlı sürümle değiştirin. Daha sonra [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) genel profil ortam değişkenlerini başlatmak ve ana bilgisayarı yeniden başlatmak için araç. Ardından, profil oluşturucu de başlatın.  
  
 İzleme eklenmiş bileşen yürütüldüğünde, zamanlama verileri bir veri dosyası otomatik olarak toplanır. Duraklatma ve veri toplama sırasında profil oluşturma oturumu sürdürün.  
  
 Profil oluşturma oturumu sona erdirmek için kapatmak [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] bileşeni barındıran ve profil oluşturucu açıkça Kapat çalışan işlemi. Çoğu durumda, bir oturumun sonunda profil ortam değişkenleri temizleme öneririz.  
  
## <a name="start-to-profile"></a>Profile Başlat  
  
#### <a name="to-instrument-an-aspnet-web-component-and-start-profiling"></a>Bir ASP.NET web bileşeni izleme ve profil oluşturmayı başlatmak için  
  
1.  Bir komut istemi penceresi açın.  
  
2.  Kullanım **Vsınstr** hedef uygulama izleme eklenmiş bir sürümünü oluşturmak için aracı. Gerekirse, uygulama ikili dosyaları ASP.NET ana bilgisayarda izleme eklenmiş ikili dosyalar ile değiştirin.  
  
3.  Ortam değişkenleri profil .NET başlatır. Komut İstemi penceresinde yazın:  
  
     **VSPerfClrEnv /globaltraceon**  
  
4.  Bilgisayarı yeniden başlatın.  
  
5.  Bir komut istemi penceresi açın. Gerekirse, profil oluşturucu Araçlar yolunu ayarlayın.  
  
6.  Profil Oluşturucu başlatın. Tür:  
  
     **VSPerfCmd /start:trace/Output:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md)**: izleme** seçeneği profil oluşturucu başlatır.  
  
    -   [/Çıkış](../profiling/output.md)**:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile` Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     İle aşağıdaki seçeneklerden birini kullanabilirsiniz **/start:trace** seçeneği.  
  
    > [!NOTE]
    >  **/User** ve **/crosssession** seçenekleri ASP.NET uygulamaları için genellikle gerekli.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|ASP.NET çalışan işlemin sahibi olan hesabın etki alanı ve kullanıcı adını belirtir. İşlem oturum açan kullanıcının başka bir kullanıcı olarak çalışıyorsa, bu seçeneği gereklidir. İşlem sahibi listelenen **kullanıcı adı** sütunu **işlemleri** sekmesi Windows Görev Yöneticisi'nin.|  
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturum açma oturumları işlemleri profil oluşturma. ASP.NET uygulamasını farklı bir oturumda çalışıyorsa, bu seçeneği gereklidir. Oturum kimliği sütununda listelendiğini oturum konumlandırıldığı **işlemleri** sekmesi Windows Görev Yöneticisi'nin. **/CS** için bir kısaltma olarak belirtilen **/crosssession**.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı bir toplanır (. *etl*) dosyası.|  
    |[/globaloff](../profiling/globalon-and-globaloff.md)|Profil Oluşturucu ile veri toplama başlatmak için duraklatıldı, ekleme **/globaloff** için seçenek **/start** komut satırı. Kullanım **/globalon** profil sürdürmek için.|  
  
7.  İzleme eklenmiş bileşen içeren Web sitesini açın.  
  
## <a name="control-data-collection"></a>Veri toplamayı denetleme  
 Hedef uygulama çalışırken, başlatma ve kullanarak verileri dosyaya yazma durdurma tarafından veri toplama denetleyebilirsiniz *VSPerfCmd.exe* seçenekleri. Veri toplama denetimi, program yürütme, başlatılıyor veya uygulama kapatılmadan gibi belirli bir bölümü için veri toplamanıza olanak sağlar.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için  
  
-   Seçenekler aşağıdaki çiftleri başlatın ve veri toplama işlemini durdurun. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) işlem kimliği tarafından belirtilen işlem için veri toplama (`PID`).|  
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:** `TID`|Başlatır (**/threadon**) veya durdurulduğunda (**/threadoff**) Kimlikli iş parçacığı tarafından belirtilen iş parçacığı için veri toplama (`TID`).|  
  
## <a name="end-the-profiling-session"></a>Profil oluşturma oturumunu sona erdirme  
 Profil oluşturma oturumu sona erdirmek için kapatmak [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması ve Internet Information Services (IIS) kullanan **IISReset** kapatmak için komut [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] çalışan işlemi. Çağrı **VSPerfCmd** [shutdown](../profiling/shutdown.md) profil oluşturucu devre dışı bırakma ve profil oluşturma veri dosyası kapatmak için seçeneği.  
  
 **VSPerfClrEnv /globaloff** komutu profil ortam değişkenleri temizler. Yeni ortam ayarlarının uygulanması için bilgisayarı yeniden başlatmanız gerekir.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için  
  
1.  Kapat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması.  
  
2.  Kapat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] çalışan işlemi. Tür:  
  
     **IISReset/stop**  
  
3.  Profil Oluşturucu kapatın. Tür:  
  
     **VSPerfCmd Shutdown**  
  
4.  (İsteğe bağlı). Profil oluşturma ortam değişkenleri temizleyin. Tür:  
  
     **VSPerfCmd /globaloff**  
  
5.  Bilgisayarı yeniden başlatın.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Profil ASP.NET web uygulamaları](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [İzleme yöntemi veri görünümleri](../profiling/instrumentation-method-data-views.md)