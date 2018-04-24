---
title: 'Nasıl yapılır: .NET hizmetini izleme ve ayrıntılı zamanlama verileri profil oluşturucu komut satırını kullanarak toplama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 10ed7c260b89259ec86b7b2ce2fc7ceed7d4c9ce
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-instrument-a-net-service-and-collect-detailed-timing-data-by-using-the-profiler-command-line"></a>Nasıl yapılır: Profil Oluşturucu Komut Satırını Kullanarak bir .NET Hizmetini İzleme ve Ayrıntılı Zamanlama Verileri Toplama

Bu konu, aracı için Visual Studio profil oluşturma araçları komut satırı araçlarını kullanmayı açıklar bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] hizmet ve ayrıntılı zamanlama verileri toplama.

> [!NOTE]
> Bilgisayar başlatıldıktan sonra hizmeti yeniden başlatılamıyor, bir hizmeti izleme yöntemiyle profil olamaz, yalnızca işletim sistemi başladığında, bu tür bir hizmet başlatır.
>
> Profil oluşturma araçları komut satırı araçları \Team Tools\Performance araçları alt dizininde bulunan [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64 bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).
>
> Profil oluşturma çalışmaya katman etkileşim verileri ekleme belirli yordamları profil oluşturma araçları komut satırıyla gerektirir. Bkz: [katman etkileşim verileri toplama](../profiling/adding-tier-interaction-data-from-the-command-line.md).

Ayrıntılı zamanlama verileri toplamak için bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] hizmeti kullandığınız izleme metodunu kullanarak [VSInstr.exe](../profiling/vsinstr.md) bileşenin izleme eklenmiş bir sürümünü oluşturmak için aracı. Ardından hizmetinin izlenmiş olmayan sürümü Araçlı sürümüyle hizmeti el ile başlatmak için yapılandırıldığından emin yapmadan değiştirin. Kullandığınız [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) aracı genel profil ortam değişkenlerini başlatmak ve ana bilgisayarı yeniden başlatın. Ardından, profil oluşturucu de başlatın.

Hizmet başlatıldığında, zamanlama verileri bir veri dosyası otomatik olarak toplanır. Duraklatma ve veri toplama sırasında profil oluşturma oturumu sürdürün.

Profil oluşturma oturumu sonlandırmak için hizmetini kapatmak ve profil oluşturucu açıkça kapatın. Çoğu durumda, bir oturumun sonunda profil ortam değişkenleri temizleme öneririz.

## <a name="starting-the-application-with-the-profiler"></a>Profil Oluşturucu ile uygulama başlatma

1. Bir komut istemi penceresi açın.

2. Kullanım **Vsınstr** hizmeti ikili Araçlı bir sürümünü oluşturmak için aracı.

3. Özgün ikili Araçlı sürümle değiştirin. Windows Hizmet Denetimi Yöneticisi'nde, hizmet başlatma türünü manuel olarak ayarlandığından emin olun.

4. Initialize [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] ortam değişkenleri profil oluşturma. Tür:

     **VSPerfClrEnv /globaltraceon**

5. Bilgisayarı yeniden başlatın.

6. Bir komut istemi penceresi açın.

7. Profil Oluşturucu başlatın. Tür:

     **VSPerfCmd /start:trace/Output:** `OutputFile` [`Options`]

    - [/Start](../profiling/start.md)**: izleme** seçeneği profil oluşturucu başlatır.

    - [/Çıkış](../profiling/output.md)**:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile` Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.

     Aşağıdaki seçenekler herhangi birini kullanabilirsiniz **/start:trace** seçeneği.

    > [!NOTE]
    > **/User** ve **/crosssession** seçenekleri profil oluşturma hizmetleri için genellikle gerekli.

    |Seçenek|Açıklama|
    |------------|-----------------|
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Profili işleme sahip hesabın etki alanı ve kullanıcı adını belirtir. Bu seçenek, yalnızca işlem oturum açan kullanıcının başka bir kullanıcı olarak çalışıyorsa gereklidir. İşlem sahibi, Windows Görev Yöneticisi'nin İşlemler sekmesinde kullanıcı adı sütununda listelenir.|
    |[/crosssession](../profiling/crosssession.md)|Etkinleştirir, diğer oturumlarda işlemleri profil oluşturma. Bu seçenek, uygulamanın farklı bir oturumda çalışıyorsa gereklidir. Oturum kimliği, Windows Görev Yöneticisi'nin İşlemler sekmesinde oturum kimliği sütununda listelenir. **/CS** için bir kısaltma olarak belirtilen **/crosssession**.|
    |[/waitstart](../profiling/waitstart.md)[**:**`Interval`]|Bir hata döndürmeden önce başlatmak profil oluşturucu için beklenecek saniye sayısını belirtir. Varsa `Interval` belirtilmezse, profil oluşturucu sonsuza kadar bekler. Varsayılan olarak, **/start** hemen döndürür.|
    |[/globaloff](../profiling/globalon-and-globaloff.md)|Profil Oluşturucu ile veri toplama başlatmak için duraklatıldı, ekleme **/globaloff** için seçenek **/start** komut satırı. Kullanım **/globalon** profil sürdürmek için.|
    |[/ sayacı](../profiling/counter.md) **:** `Config`|İşlemci performansı sayaç yapılandırma dosyasında belirtilen bilgi toplar. Sayaç bilgileri her profil olay, toplanan veriler eklenir.|
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında toplanacak olay Windows için izleme (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|

8. Windows Hizmet Denetimi Yöneticisi'nden hizmetini başlatın.

## <a name="controlling-data-collection"></a>Veri toplama denetimi

Hizmet çalışırken kullanabileceğiniz **VSPerfCmd.exe** Profil Oluşturucu veri dosyası için veri yazma durdurmak ve başlatmak için Seçenekler. Veri toplama denetimi, program yürütme, başlatılıyor veya hizmeti kapatılıyor gibi belirli bir bölümü için veri toplamanıza olanak sağlar.

- Aşağıdaki çiftleri **VSPerfCmd** seçenekleri başlatma ve durdurma veri toplama. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.

    |Seçenek|Açıklama|
    |------------|-----------------|
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) işlem kimliği tarafından belirtilen işlem için veri toplama (`PID`).|
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:** `TID`|Başlatır (**/threadon**) veya durdurulduğunda (**/threadoff**) Kimlikli iş parçacığı tarafından belirtilen iş parçacığı için veri toplama (`TID`).|

## <a name="ending-the-profiling-session"></a>Profil oluşturma oturumu sona erdirme

Profil oluşturma oturumu sona erdirmek için izleme eklenmiş bileşenini çalıştıran hizmetini durdurun ve ardından çağıran **VSPerfCmd** [shutdown](../profiling/shutdown.md) profil oluşturucu kapatmak ve profil oluşturma veri dosyası kapatmak için seçeneği. **VSPerfClrEnv /globaloff** komutu profil ortam değişkenleri temizler.

Yeni ortam ayarlarının uygulanması için bilgisayarı yeniden başlatmanız gerekir.

1. Hizmet Denetimi Yöneticisi'nden hizmetini durdurun.

2. Profil Oluşturucu kapatın. Tür:

     **VSPerfCmd Shutdown**

3. Tüm profil oluşturmayı tamamladıktan sonra profil ortam değişkenleri temizleyin. Tür:

     **VSPerfClrEnv /globaloff**

4. İzleme eklenmiş modülü özgün ile değiştirin. Gerekirse, hizmet başlangıç türünü yeniden yapılandırın.

5. Bilgisayarı yeniden başlatın.

## <a name="see-also"></a>Ayrıca bkz.

[Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)  
[İzleme Metodu Veri Görünümleri](../profiling/instrumentation-method-data-views.md)