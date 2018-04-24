---
title: 'Nasıl yapılır: dinamik olarak derlenmiş bir ASP.NET Web uygulamasını izleme ve ayrıntılı zamanlama verileri Profil Oluşturucu ile komut satırını kullanarak toplama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 7c1f3073b1b3ebeb142805e5d34097c82e038e67
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-detailed-timing-data-with-the-profiler-by-using-the-command-line"></a>Nasıl yapılır: Profil Oluşturucu ile Komut Satırını Kullanarak Dinamik Olarak Derlenmiş bir ASP.NET Web Uygulamasını İzleme ve Ayrıntılı Zamanlama Verileri Toplama

Bu konuda dinamik olarak derlenmiş ayrıntılı zamanlama verileri toplamak için profil oluşturma Visual Studio Araçları komut satırı araçlarını kullanmayı açıklar [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] izleme profili oluşturma yöntemi kullanarak uygulama.

> [!NOTE]
> Profil oluşturma araçları komut satırı araçları \Team Tools\Performance araçları alt dizininde bulunan [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64-bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).

Performans verileri toplamak için bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulamasını etkinleştirmek için hedef uygulamanın web.config dosyasında değişiklik [VSInstr.exe](../profiling/vsinstr.md) dinamik olarak derlenmiş uygulama dosyaları işaretleme aracı. Daha sonra [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) profil oluşturmayı etkinleştirmek için Web sunucusunda uygun ortam değişkenlerini ayarlamak için aracı ve bilgisayarı yeniden başlatın.

Profil Oluşturucu başlatın ve ardından hedef uygulama çalıştırın. Profil Oluşturucu uygulamaya bağlı olsa da, duraklatma ve veri toplama sürdürme. Profil bitirdikten sonra uygulamayı kapatın, Internet Information Services (IIS) çalışan işlem kapatın ve ardından profil oluşturucuyu kapatın. Profil oluşturma iş tamamlandığında, web.config dosyasını ve Web sunucusu özgün durumlarına geri yükleyin.

## <a name="configuring-the-aspnet-web-application-and-the-web-server"></a>ASP.NET Web uygulaması ve Web sunucusu yapılandırma

1. Hedef uygulamanın web.config dosyasını değiştirin. Bkz: [nasıl yapılır: Gereci için Web.Config dosyalarını değiştirme ve dinamik olarak derlenmiş ASP.NET Web uygulamalarında profil](../profiling/how-to-modify-web-config-files-to-instrument-and-profile-dynamically-compiled-aspnet-web-applications.md).

2. Bir komut istemi penceresi açın.

3. Profil oluşturma ortam değişkenleri başlatır. Tür:

     **VSPerfClrEnv /globaltraceon**

    - **/globaltraceon** izleme metodunu kullanarak profil sağlar.

4. Bilgisayarı yeniden başlatın.

## <a name="running-the-profiling-session"></a>Profil oluşturma oturumu çalıştırma

1. Bir komut istemi penceresi açın.

2. Profil Oluşturucu başlatın. Tür:

     **VSPerfCmd**[/start](../profiling/start.md) **: izleme**[/çıkış](../profiling/output.md) **:** `OutputFile` [`Options`]    

    - **/Start:trace** seçeneği profil oluşturucu başlatır.

    - **/Çıktı:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile` Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.

     İle aşağıdaki seçeneklerden birini kullanabilirsiniz **/start:trace** seçeneği.

    > [!NOTE]
    > **/User** ve **/crosssession** seçenekleri ASP.NET uygulamaları için genellikle gerekli.

    |Seçenek|Açıklama|
    |------------|-----------------|
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|ASP.NET çalışan işlemin sahibi olan hesabın etki alanı ve kullanıcı adını belirtir. İşlem oturum açan kullanıcının başka bir kullanıcı olarak çalışıyorsa, bu seçeneği gereklidir. İşlem sahibi, Windows Görev Yöneticisi'nin İşlemler sekmesinde kullanıcı adı sütununda listelenir.|
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturum açma oturumları işlemleri profil oluşturma. ASP.NET uygulamasını farklı bir oturumda çalışıyorsa, bu seçeneği gereklidir. Oturum tanımlayıcısı İşlemler sekmesinde Windows Görev Yöneticisi'nin oturum kimliği sütununda listelenir. **/CS** için bir kısaltma olarak belirtilen **/crosssession**.|
    |[/globaloff](../profiling/globalon-and-globaloff.md)|Profil Oluşturucu veri koleksiyonu duraklatıldı başlatır. Kullanım [/globalon](../profiling/globalon-and-globaloff.md) profil sürdürmek için.|
    |[/ sayacı](../profiling/counter.md) **:** `Config`|Belirtilen işlemci performans sayacı bilgileri toplar `Config`. Sayaç bilgileri her profil olay, toplanan verilere eklenir.|
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|

3. Başlat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması normal şekilde.

## <a name="controlling-data-collection"></a>Veri toplama denetimi

Hedef uygulama çalışırken, başlatma ve kullanarak profil oluşturucu veri dosyası için veri yazma durdurma tarafından veri toplama denetleyebilirsiniz **VSPerfCmd.exe** seçenekleri. Veri toplama denetimi, program yürütme, başlatılıyor veya uygulama kapatılmadan gibi belirli bir bölümü için veri toplamanıza olanak sağlar.

- Seçenekler aşağıdaki çiftleri başlatın ve veri toplama işlemini durdurun. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.

    |Seçenek|Açıklama|
    |------------|-----------------|
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) işlem kimliği tarafından belirtilen işlem için veri toplama (`PID`).|
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:** `TID`|Başlatır (**/threadon**) veya durdurulduğunda (**/threadoff**) Kimlikli iş parçacığı tarafından belirtilen iş parçacığı için veri toplama (`TID`).|

- Aynı zamanda **VSPerfCmd.exe**[/işaretlemek](../profiling/mark.md) profil işareti veri dosyasına eklemek için seçeneği. **/İşaretlemek** komut tanımlayıcı, bir zaman damgası ve bir kullanıcı tanımlı isteğe bağlı bir metin dizesi ekler. İşaretleri Profil Oluşturucusu rapor ve veri görünümleri verilerini filtrelemek için kullanılabilir.

## <a name="ending-the-profiling-session"></a>Profil oluşturma oturumu sona erdirme

Profil oluşturma oturumu sona erdirmek için hedef kapatmak [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması, profili işlemini durdurun ve sonra Profil Oluşturucu kapatmak için IIS'yi sıfırlayın.

1. Kapat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması.

2. Kapat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Internet Information Services (IIS) sıfırlama tarafından çalışan işlemi. Tür:

     **IISReset/stop**

3. Profil Oluşturucu kapatın. Tür:

     **VSPerfCmd**[Shutdown](../profiling/shutdown.md)

4. IIS'yi yeniden başlatın. Tür:

     **IISReset/Start**

## <a name="restoring-the-application-and-computer-configuration"></a>Uygulama ve bilgisayar yapılandırmasını geri yükleme

Tüm profil oluşturmayı tamamladıktan sonra web.config dosyasını değiştirin, profil ortam değişkenleri temizleyin ve sunucu ve uygulama içinde profil önce oldukları durumları geri yüklemek için bilgisayarı yeniden başlatın.

1. Web.config dosyasının özgün dosyanın bir kopyasını değiştirin.

2. Profil oluşturma ortam değişkenleri temizleyin. Tür:

     **VSPerfCmd /globaloff**

3. Bilgisayarı yeniden başlatın.

## <a name="see-also"></a>Ayrıca bkz.

[ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)  
[İzleme Metodu Veri Görünümleri](../profiling/instrumentation-method-data-views.md)