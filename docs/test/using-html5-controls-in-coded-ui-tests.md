---
title: "Kodlanmış UI testleri Visual Studio'da HTML5 denetimleri kullanma | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: d61f35e4c3dc772f761b1107f686e961ec34db91
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="using-html5-controls-in-coded-ui-tests"></a>Kodlanmış UI Testlerinde HTML5 Denetimleri Kullanma

Kodlanmış UI testleri bazı Internet Explorer 9 ve Internet Explorer 10 dahil HTML5 denetimler için destek içerir.

 **Gereksinimler**

-   Visual Studio Enterprise

> [!WARNING]
>  Internet Explorer 10 önce sürümlerde, Internet Explorer işlemi karşılaştırıldığında daha yüksek bir ayrıcalık düzeyinde kodlanmış UI testleri çalıştırmak mümkün. Kodlanmış UI testleri üzerinde Internet Explorer 10 çalıştırırken, kodlanmış UI testi ve Internet Explorer işlemi aynı ayrıcalık düzeyinde olması gerekir. Internet Explorer 10 daha güvenli Appcontaıner özellikleri nedeniyle budur.

> [!WARNING]
>  Internet Explorer 10'kodlanmış UI testi oluşturursanız, Internet Explorer 9 veya Internet Explorer 8 kullanarak çalışmayabilir. Internet Explorer 10 HTML5 denetimleri ses, Video, ProgressBar ve kaydırıcı gibi içerdiğinden budur. Bu HTML5 denetimleri, Internet Explorer 9 veya Internet Explorer 8 tarafından tanınmaz. Benzer şekilde, Internet Explorer 9 kullanarak kodlanmış UI testleri, Internet Explorer 8 tarafından tanınmayacak bazı HTML5 denetimleri de içerebilir.

## <a name="supported-html5-controls"></a>Desteklenen HTML5 denetimleri
 Kodlanmış UI testleri kaydı, yürütme ve doğrulama aşağıdaki HTML5 denetimleri için destek içerir:

-   [Ses denetimi](#UsingHTML5ControlsCodedUITestsAudio)

-   [Video denetimi](#UsingHTML5ControlsCodedUITestsVideo)

-   [Kaydırıcı](#UsingHTML5ControlsCodedUITestsSlider)

-   [ProgressBar](#UsingHTML5ControlsCodedUITestsProgressBar)

###  <a name="UsingHTML5ControlsCodedUITestsAudio"></a> Ses denetimi
 **Ses denetimi:** HTML5 ses denetim eylemleri doğru şekilde kaydedilir ve çalınma.

 ![HTML5 ses denetimi](../test/media/codedui_html5_audio.png "CodedUI_HTML5_Audio")

|Eylem|Kaydetme|Oluşturulan kod|
|------------|---------------|--------------------|
|**Ses çalma**<br /><br /> Doğrudan denetim veya denetimlerin bağlam menüsünden.|Yürüt \<adı > 00:00: 00'dan ses|HtmlAudio.Play(TimeSpan)|
|**Ses belirli bir zaman için arama**|Arama \<adı > 00:01:48 ses|HtmlAudio.Seek(TimeSpan)|
|**Duraklatma ses**<br /><br /> Doğrudan denetim veya denetimlerin bağlam menüsünden.|Duraklatma \<adı > 00:01:53 adresindeki ses|HtmlAudio.Pause(TimeSpan)|
|**Sessiz ses**<br /><br /> Doğrudan denetim veya denetimlerin bağlam menüsünden.|Sessiz \<adı > ses|HtmlAudio.Mute()|
|**Ses sesi Aç**<br /><br /> Doğrudan denetim veya denetimlerin bağlam menüsünden.|Sesi Aç \<adı > ses|HtmlAudio.Unmute()|
|**Ses düzeyini değiştirme**|Ayarlama hacmi \<adı > %79 ses|HtmlAudio.SetVolume(float)|

 Aşağıdaki özellikler HtmlAudio için kullanılabilir ve bir onaylama hepsinde ekleyebilirsiniz:

```
string AutoPlay
string Controls
string CurrentSrc
string CurrentTime
string CurrentTimeAsString
string Duration
string DurationAsString
string Ended
string Loop
string Muted
string Paused
string PlaybackRate
string ReadyState
string Seeking
string Src
string Volume

```

 **Arama özellikleri:** arama özelliklerinin `HtmlAudio` olan `Id`, `Name` ve `Title`.

 **Filtre özellikleri:** filtre özelliklerini `HtmlAudio` olan `Src`, `Class`, `ControlDefinition` ve `TagInstance`.

> [!NOTE]
>  Arama ve Duraklat için geçen süreyi önemli olabilir. Belirtilen süre kadar kodlanmış UI Testi kayıttan yürütme sırasında bekleyecek `(TimeSpan)` ses duraklatma önce. Özel bazı koşullar tarafından Duraklat komutunu basarsa önce belirtilen süre geçtiyse, bir özel durum.

###  <a name="UsingHTML5ControlsCodedUITestsVideo"></a> Video denetimi
 **Video denetimi:** HTML5 videosunu denetim eylemleri doğru şekilde kaydedilir ve çalınma.

 ![HTML5 Video denetimi](../test/media/codedui_html5_video.png "CodedUI_HTML5_Video")

|Eylem|Kaydetme|Oluşturulan kod|
|------------|---------------|--------------------|
|**Video oynatma**<br /><br /> Doğrudan denetim veya denetimlerin bağlam menüsünden.|Yürüt \<adı > 00:00: 00'dan Video|HtmlVideo.Play(TimeSpan)|
|**Video belirli bir zaman için arama**|Arama \<adı > 00:01:48 Video|HtmlVideo.Seek(TimeSpan)|
|**Videoyu Duraklat**<br /><br /> Doğrudan denetim veya denetimlerin bağlam menüsünden.|Duraklatma \<adı > 00:01:53 adresindeki Video|HtmlVideo.Pause(TimeSpan)|
|**Sessiz video**<br /><br /> Doğrudan denetim veya denetimlerin bağlam menüsünden.|Sessiz \<adı > Video|HtmlVideo.Mute()|
|**Video Sesi Aç**<br /><br /> Doğrudan denetim veya denetimlerin bağlam menüsünden.|Sesi Aç \<adı > Video|HtmlVideo.Unmute()|
|**Video hacmi değiştirme**|Ayarlama hacmi \<adı > %79 Video||

 HtmlAudio tüm özelliklerini HtmlVideo için kullanılabilir. Ayrıca, şu üç özellik de kullanılabilir. Onaylama işlemi hepsinde eklenebilir.

```
string Poster
string VideoHeight
string VideoWidth

```

 **Arama özellikleri:** arama özelliklerinin `HtmlVideo` olan `Id`, `Name` ve `Title`.

 **Filtre özellikleri:** filtre özelliklerini `HtmlVideo` olan `Src`, `Poster`, `Class`, `ControlDefinition` ve `TagInstance`.

> [!NOTE]
>  Geri Sar veya-30s veya +30s etiketleri kullanarak video ileri sarma, bunu uygun zaman arama toplanacak.

###  <a name="UsingHTML5ControlsCodedUITestsSlider"></a> Kaydırıcı
 **Kaydırıcı denetimi:** HTML5 kaydırıcı denetimi eylemlerini doğru şekilde kaydedilir ve çalınma.

 ![HTML5 kaydırıcı denetimi](../test/media/codedui_html5_slider.png "CodedUI_HTML5_Slider")

|Eylem|Kaydetme|Oluşturulan kod|
|------------|---------------|--------------------|
|**Kaydırıcı konumda ayarlayın**|Kümesine konumu \<x > içinde \<adı > kaydırıcı|HtmlSlider.ValueAsNumber=\<x>|

 Aşağıdaki özellikler HtmlSlider için kullanılabilir ve onaylama hepsinde eklenebilir:

```
string Disabled
string Max
string Min
string Required
string Step
string ValueAsNumber
```

###  <a name="UsingHTML5ControlsCodedUITestsProgressbar"></a> ProgressBar
 **ProgreesBar denetimi:** ProgressBar olduğu interactable olmayan bir denetim. Onaylar ekleyebilirsiniz `Value` ve `Max` bu denetimin özelliklerini.

 ![HTML5 ProgressBar denetimi](../test/media/codedui_html5_progressbar.png "CodedUI_HTML5_ProgressBar")

## <a name="see-also"></a>Ayrıca bkz.

- [HTML öğeleri](http://go.microsoft.com/fwlink/?LinkID=232441)
- [Kodunuzu Test Etmek için UI Otomasyonunu Kullanma](../test/use-ui-automation-to-test-your-code.md)
- [Kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md)
- [Kodlanmış UI Testleri ve Eylem Kayıtları için Desteklenen Yapılandırmalar ve Platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
