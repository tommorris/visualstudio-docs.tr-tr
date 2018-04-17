---
title: Erişilebilirlik ipuçları ve püf noktaları Visual Studio için | Microsoft Docs
ms.custom: ''
ms.date: 09/15/2017
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- accessibility [Visual Studio]
ms.assetid: 6b491d88-f79e-4686-8841-857624bdcfda
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 06f378c3ac0cfc808094170c37792399812538bf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="accessibility-tips-and-tricks-for-visual-studio"></a>Erişilebilirlik ipuçları ve püf noktaları Visual Studio için
> [!TIP]
> Son erişilebilirlik güncelleştirmeleri hakkında daha fazla bilgi için bkz: [Visual Studio 2017 sürüm 15.3 erişilebilirlik geliştirmeleri](https://blogs.msdn.microsoft.com/visualstudio/2017/08/14/accessibility-improvements-in-visual-studio-2017-version-15-3/) blog postası.

Visual Studio, ekran okuyucuların ve diğer yardımcı teknolojiler ile uyumlu erişilebilirlik özelliğine sahiptir. Bu konu yalnızca klavye görevleri gerçekleştirmek için kullanabilirsiniz ve görünürlüğünü artırmak için yüksek karşıtlıklı tema kullanma hakkında bilgi içeren ortak kısayol tuş birleşimleri listeler. De ek açıklamaları kodunuzu hakkında yararlı bilgiler ortaya çıkarmak için nasıl kullanılacağını gösterir ve ses ayarlama yapı ve kesme olayları Desteleri.

## <a name="save-your-ide-settings"></a>IDE ayarlarınızı kaydedin  
 Pencere düzeninizi, klavye kısayol düzenini ve diğer tercihlerinizi kaydederek IDE deneyiminizi özelleştirebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).  

## <a name="modify-your-ide-for-high-contrast-viewing"></a>Yüksek karşıtlıklı görüntülemek için IDE değiştirme
Bazı çok kişi bazı renkler görmek daha zordur. Daha fazla Karşıtlık, kod olarak istiyor, ancak tipik "Yüksek Karşıtlık" temaları kullanmak istemediğiniz şimdi "Mavi (ek Karşıtlık)" tema sunuyoruz.

  ![Mavi fazladan karşıtlık teması ve mavi tema karşılaştırmak](media/blue-extra-contrast-theme.png "mavi fazladan karşıtlık teması mavi tema arasındaki farkı bakın")

## <a name="use-annotations-to-reveal-useful-information-about-your-code"></a>Kodunuzu hakkında yararlı bilgiler ortaya çıkarmak için ek açıklamalarını kullanma

Visual Studio düzenleyicisinde "vb. yer işaretleri, özellikleri ve bir satıra lightbulbs, hata ve uyarı"dalgalı çizgiler", gibi kodunun belirli noktalarda özellikleri hakkında bilmeniz sağlayan birçok metin adornments" içerir. Bulabilir ve bu adornments arasında gezinmek yardımcı olması için ayarlama "Satırı ek açıklamaları Göster" komutunu kullanabilirsiniz.

  ![Satır ek açıklamaları Göster komut kümesini kullanmak](media/show-line-annotations-command-set.png "satır ek açıklamaları Göster komut kümesi gösterilmektedir")

## <a name="access-toolbars-by-using-shortcut-key-combinations"></a>Kısayol tuş birleşimleri kullanarak erişim araç çubukları
Birçok aracı windows yapmak gibi Visual Studio IDE araç çubukları vardır. Aşağıdaki kısayol tuş birleşimleri bunları erişmenize yardımcı olur.

|Özellik|Açıklama|Tuş bileşimini|  
|-------------|-----------------|---------------------|  
|IDE araç çubukları|Standart araç çubuğundaki ilk düğmesini seçin.|**ALT**, **CTRL** + **SEKMESİ**|  
|Araç penceresi araç çubukları|Araç çubukları araç penceresinde odağı taşır. <br> <br> **Not:** bu çoğu aracı windows için ancak yalnızca odağı araç penceresinde olduğunda çalışır. Ayrıca, ALT tuşu önce SHIFT tuşunu seçmeniz gerekir. Takım Gezgini gibi bazı aracı Windows ALT anahtar seçilmeden önce bir süre için SHIFT tuşuna basılı gerekir.|**SHIFT** + **ALT**|
|Araç Çubukları|Listedeki ilk öğe sonraki araç çubuğunu (araç çubuğu odağa sahip olduğunda) gidin.|**CTRL** + **SEKMESİ**|

### <a name="other-useful-shortcut-key-combinations"></a>Diğer kullanışlı kısayol tuş birleşimleri  
Bazı diğer yararlı bir kısayol tuş bileşimlerini arasında şunlar yer alır.

|Özellik|Açıklama|Tuş bileşimini|  
|-------------|-----------------|---------------------|  
|IDE|Yüksek Karşıtlık kapatabilirsiniz. <br> <br> **Not:** standart Windows kısayolu|**Sol ALT + sol üst karakter + yazdırma EKRANI**|  
|İletişim kutusu|İletişim kutusunda onay kutusunu seçeneğinin işaretini kaldırın veya seçin. <br> <br> **Not:** standart Windows kısayolu|**BOŞLUK ÇUBUĞU**|  
|Bağlam menüleri|Bir içerik (sağ tıklatma) menüsünü açın. <br> <br> **Not:** standart Windows kısayolu|**SHIFT** + **F10**|
|Menüler|Kısayol tuşlarını kullanarak hızlı bir şekilde bir menü öğesine erişin. Seçin **ALT** menü komutu etkinleştirmek için altı çizili harfler arkasından anahtarı. Örneğin, Visual Studio Proje Aç iletişim kutusu görüntülemek için seçmeniz **ALT** + **F** + **O**  +  **P**.  <br><br> **Not:** standart Windows kısayolu|**ALT** + **[harfi]**|
|Araç penceresi|Araç kutusu sekmeler arasında taşıyın.|**CTRL** + **UPARROW**<br /><br /> and<br /><br /> **CTRL** + **DOWNARROW**|  
|Araç penceresi|Bir denetimi, bir form veya tasarımcıya Araç Kutusu'ndan ekleyin.|**GİRİN**|  
|Klavye, ortam, Seçenekler iletişim kutusu|Girilen bir tuş bileşimini silme **basın kısayol tuşları** seçeneği.|**GERİ AL**|  

> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir.  


## <a name="use-the-sound-applet-to-set-build-and-breakpoint-cues"></a>Ses uygulaması derleme ve kesme noktası yardımlar ayarlamak için kullanın
Visual Studio program olaylarına ses atamak için Windows Ses uygulamasını kullanabilirsiniz. Özellikle, aşağıdaki program olaylarına ses atayabilirsiniz:

 * Kesme noktası isabet
 * Derleme iptal edildi
 * Oluşturma başarısız oldu
 * Yapı başarılı oldu

İşte nasıl.

1. İçinde **arama** kutusunu türü olan Windows 10 çalıştıran bir bilgisayarda **değiştirmek sistem sesleri**.

  ![Windows 10 arama kutusuna](media/type-here-to-search.png "türü ses arama kutusuna Windows 10 çalıştıran bir bilgisayarda")

  (Alternatif olarak, etkin Cortana varsa, "Hey Cortana" deyin ve "Sistem seslerini Değiştir" komutunu verin.)

2. Çift **değiştirmek sistem sesleri**.

  ![Arama sonuçlarında Windows 10'da](media/change-system-sounds.png "çift arama sonuçlarında sistem seslerini Değiştir")

3. İçinde **ses** iletişim kutusu, tıklatın **ses** sekmesi. <br><br>
 Ardından **Program olayları**, kaydırın **Microsoft Visual Studio**, seçtiğiniz olaylara uygulamak istediğiniz ses seçin.

  ![Windows 10 ses uygulaması ses sekmesinde](media/sound-applet.png "çift arama sonuçlarında sistem seslerini Değiştir")

4. **Tamam**'ı tıklatın.



## <a name="see-also"></a>Ayrıca bkz.  
* [Visual Studio'nun Erişilebilirlik Özellikleri](../../ide/reference/accessibility-features-of-visual-studio.md)
  * [Nasıl Yapılır: Visual Studio'da Menüleri ve Araç Çubuklarını Özelleştirme](../../ide/how-to-customize-menus-and-toolbars-in-visual-studio.md)
* [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md)
* [Microsoft Erişilebilirlik](https://www.microsoft.com/Accessibility)
