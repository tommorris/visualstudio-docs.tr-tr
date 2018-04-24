---
title: 'Nasıl yapılır: Profil oluşturucu komut satırını kullanarak bellek verileri toplamak için bir .NET Framework bağımsız uygulamasına ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 6c81443332a05fbd60a295613c5f34c579482199
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-attach-the-profiler-to-a-net-framework-stand-alone-application-to-collect-memory-data-by-using-the-command-line"></a>Nasıl yapılır: Komut Satırını Kullanarak Bellek Verileri Toplamak için Profil Oluşturucuyu bir .NET Framework Bağımsız Uygulamasına Ekleme

Bu konu, çalışan bir .NET Framework tek başına (istemci) uygulamaya profil oluşturucu ekleme ve bellek verileri toplamak için Visual Studio profil oluşturma araçları komut satırı araçlarını kullanmayı açıklar.

> [!NOTE]
> Profil oluşturma araçları komut satırı araçları \Team Tools\Performance araçları alt dizininde bulunan [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64-bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).

Bir .NET Framework uygulama ve toplama bellek verileri eklemek için kullanmanız gerekir [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) aracı hedef uygulama başlatılmadan önce uygun ortam değişkenlerini başlatılamadı. Profil Oluşturucu uygulamaya eklendiğinde kullanabileceğiniz **VSPerfCmd.exe** aracı veri toplamayı durdur.

Profil oluşturma oturumu sona erdirmek için profil oluşturucu tüm profili işlemlerini ayrılmış olmalıdır ve profil oluşturucu açıkça kapatılmalıdır. Çoğu durumda, bir oturumun sonunda profil ortam değişkenleri temizleme öneririz.

## <a name="attaching-the-profiler"></a>Profil Oluşturucu ekleme

### <a name="to-attach-the-profiler-to-a-running-net-framework-application"></a>Profil Oluşturucu çalışan bir .NET Framework uygulama eklemek için

1. Bir komut istemi penceresi açın.

2. Profil oluşturma ortam değişkenleri başlatır. Tür:

     **VSPerfClrEnv** {**/samplegc** &#124; **/samplegclife**} [**/samplelineoff**]

    - **/Samplegc** ve **/samplegclife** seçenekleri mi, yoksa yalnızca bellek ayırma verileri toplamak için bellek ayırma ve nesne yaşam süresi verilerini toplamak için belirtin. Tek bir seçeneği belirtilmelidir.

        |Seçenek|Açıklamaları|
        |------------|------------------|
        |**/samplegc**|Bellek ayırma veri toplar.|
        |**/samplegclife**|Bellek ayırma ve nesne yaşam verisi toplar.|

    - **/Samplelineoff** seçeneği, kaynak kodu satır numarası veri koleksiyonunu devre dışı bırakır.

3. Profil Oluşturucu başlatın. Tür:

     **VSPerfCmd /start:sample/Output:** `OutputFile` [`Options`]

    - [/Start](../profiling/start.md)**: örnek** seçeneği profil oluşturucu başlatır.

    - [/Çıkış](../profiling/output.md)**:** `OutputFile` seçeneği ile gerekli **/start**. `OutputFile` Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.

     İle aşağıdaki seçeneklerden birini kullanabilirsiniz **/start:sample** seçeneği.

    |Seçenek|Açıklama|
    |------------|-----------------|
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Profili işleme sahip hesabın etki alanı ve kullanıcı adını belirtir. Bu seçenek, yalnızca işlem oturum açmış olan kullanıcı dışındaki bir kullanıcı olarak çalışıyorsa gereklidir. İşlem sahibi, Windows Görev Yöneticisi'nin İşlemler sekmesinde kullanıcı adı sütununda listelenir.|
    |[/crosssession &#124; /cs](../profiling/crosssession.md)|Etkinleştirir, diğer oturumlarda işlemleri profil oluşturma. Bu seçenek, uygulamanın farklı bir oturumda çalışıyorsa gereklidir. Oturum idenitifer İşlemler sekmesinde Windows Görev Yöneticisi'nin oturum kimliği sütununda listelenir. **/CS** için bir kısaltma olarak belirtilen **/crosssession**.|
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında toplanması için bir Windows performans sayacı belirtir.|
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullandığınız **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500 ms ' dir.|

4. Gerekirse, hedef uygulamanın normal şekilde başlatın.

5. Hedef uygulama için profil oluşturucu ekleme. Tür:

     **VSPerfCmd**[/ attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [[/targetclr](../profiling/targetclr.md)**:**`Version`]  

    - `PID` Hedef uygulama işlem Kimliğini belirtir. `ProcessName` işlemin adını belirtir. Belirttiğiniz gerçekleştiriyorsanız `ProcessName` ve aynı ada sahip birden çok işlem çalıştırıyorsanız, sonuçlar tahmin edilemez. İşlem tüm çalışan işlemleri kimliklerini Windows Görev Yöneticisi'nde görüntüleyebilirsiniz.

    - **/targetclr:** `Version` bir uygulamada birden fazla çalışma zamanı sürümü yüklendiğinde profiline ortak dil çalışma zamanı (CLR) sürümünü belirtir. İsteğe bağlı.

## <a name="controlling-data-collection"></a>Veri Toplama Denetimi

Hedef uygulama çalışırken, başlatma ve kullanarak verileri dosyaya yazma durdurma tarafından veri toplama denetleyebilirsiniz **VSPerfCmd.exe** seçenekleri. Veri toplama denetimi, program yürütme, başlatılıyor veya uygulama kapatılmadan gibi belirli bir bölümü için veri toplamanıza olanak sağlar.

### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak için

- Seçenekler aşağıdaki çiftleri başlatın ve veri toplama işlemini durdurun. Her ayrı bir komut satırı seçeneğini belirtin. Veri toplama, birden çok kez açıp kapatabilirsiniz.

    |Seçenek|Açıklama|
    |------------|-----------------|
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlatır (**/globalon**) veya durdurulduğunda (**/globaloff**) tüm işlemler için veri toplama.|
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlatır (**/processon**) veya durdurulduğunda (**/processoff**) tarafından belirtilen işlem için veri toplama `PID`.|
    |[/ attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ attach** tarafından belirtilen işlem için veri toplamaya başlar `PID` veya işlem adı (ProcName). **/ detach** belirli bir işlemin belirtilmezse, tüm işlemler veya belirtilen işlem için veri toplamayı durdurur.|

## <a name="ending-the-profiling-session"></a>Profil oluşturma oturumu sona erdirme

Profil oluşturma oturumu sona erdirmek için profil oluşturucu tüm profili işlemlerini ayrılmış olmalıdır ve profil oluşturucu açıkça kapatılmalıdır. Profil Oluşturucu uygulamadan uygulama kapatarak veya çağırarak örnekleme yöntemini kullanarak profili ayırabilirsiniz **VSPerfCmd / detach** seçeneği. Ardından çağıran **VSPerfCmd shutdown** profil oluşturucu devre dışı bırakma ve profil oluşturma veri dosyası kapatmak için seçeneği. **VSPerfClrEnv / kapalı** komutu profil ortam değişkenleri temizler.

### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumu sona erdirmek için

1. Profil Oluşturucu hedef uygulamasından ayırmak için aşağıdaki adımlardan birini gerçekleştirin:

    - Tür **VSPerfCmd / Ayır**

         -veya-

    - Hedef uygulamayı kapatın.

2. Profil Oluşturucu kapatın. Tür:

     **VSPerfCmd**[Shutdown](../profiling/shutdown.md)

3. (İsteğe bağlı) Profil oluşturma ortam değişkenleri temizleyin. Tür:

     **VSPerfCmd / kapalı**

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)  
[.NET bellek verisi görünümleri](../profiling/dotnet-memory-data-views.md)