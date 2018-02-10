---
title: "Visual Studio için R araçları ile verileri Görselleştirme | Microsoft Docs"
description: "Visual Studio'da çizim windows kullanarak, R programlarından verileri çizmek nasıl."
ms.custom: 
ms.date: 06/29/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
dev_langs:
- R
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- data-science
ms.openlocfilehash: 97e9838e46a4e0158b281f243ffda7d46044ef2d
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="creating-visual-data-plots-with-r"></a>R ile çizer görsel veri oluşturma

Çizim, bir veri Bilimcisi'nın iş akışı anahtar bir parçasıdır. R araçları için Visual Studio (RTVS)'da, tüm çizim etkinlik bu anahtar etkinlik verimliliğinizi artırmak için tasarlanmış bir veya daha fazla çizim windows çevresinde toplanır.

![Kahramanı görüntü çizme](media/plotting-hero-image.png)

Aşağıdaki video (2m 02s) içinde RTVS Çizdirmek, kısa bir tur sağlar:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ZTbKmz5RSgY" frameborder="0" allowfullscreen></iframe>

## <a name="the-plot-window"></a>Çizim penceresi

Çizimler, burada her çizim tarafından oluşturulur bir dizi bir çizim penceresi tutan bir `plot` komutu. Örneğin, kullanarak `plot(1:100)` bir zaten mevcut değilse yeni bir çizim penceresi oluşturur:

![1 ile 100 doğrusal çizim](media/plotting-1-to-100.png)

Teknik olarak konuşarak, R `plot` komutları işleme çıktılarını bir R grafik cihazına; bir çizim penceresi her çizim penceresi aygıt numarası verilen neden olan bir R grafik cihaz içeriğini oluşturur.

Çizim windows Visual Studio projeleri bağımsızdır ve yük ve projeleri kapatın gibi açık kalır.

Bir çizim oluşturma kullanır "active" çizim penceresinde herhangi önceki kaydetme çizim, çizim geçmişi (bkz [çizim geçmişi](#plot-history)). Örneğin, `plot(100:1)` ve ilk çizim aşağıya doğru satır ile değiştirilir.

Diğer tüm Visual Studio windows gibi. Özel düzenler çizim penceresi destekler (bkz [Visual Studio'da pencere düzenlerini özelleştirme](../ide/customizing-window-layouts-in-visual-studio.md). Çizim windows Visual Studio çerçevesinde farklı konumlarda yerleşik, o çerçevesinde yeniden boyutlandırılmış veya tamamen bağımsız yeniden boyutlandırma için çerçeve dışında çekilen. 

Bir çizim penceresi her zaman yeniden boyutlandırma en iyi kalite görüntü sağlamak için çizim yeniden oluşturur. Tipik olarak bir çizim çizim bir dosyaya veya bir sonraki bölümde açıklanan komutları kullanarak Pano dışarı aktarmadan önce yeniden boyutlandırma istersiniz.

## <a name="plot-window-commands"></a>Çizim penceresi komutları

Çizim pencerenin araç çoğunu aracılığıyla da uygulanabilir komutların tutan **R Araçlar > çizimleri** menüsü.

| Düğme | Komut | Açıklama | 
| --- | --- | --- |
| ![Yeni çizim penceresi düğmesi](media/plotting-toolbar-01-new-plot-window.png) | Yeni bir çizim penceresi | Ayrı çizim pencere kendi geçmişi ile oluşturur. Bkz: [birden çok çizim windows](#multiple-plot-windows). |
| ![Çizim penceresi düğmesini etkinleştirin](media/plotting-toolbar-02-activate-plot-window.png) | Çizim pencereyi etkinleştir | Etkin pencereyi, bu nedenle bu sonraki geçerli çizim penceresi ayarlar `plot` komutları pencereye işlenir. Bkz: [birden çok çizim windows](#multiple-plot-windows). Bkz: [birden çok çizim windows](#multiple-plot-windows). |
| ![Çizim Geçmişi penceresini düğmesi](media/plotting-toolbar-03-plot-history.png) | Çizim Geçmiş penceresi | Küçük resim olarak gösterilen geçmişinde tüm çizimleri ile bir pencere açılır. Bkz: [çizim geçmişi](#plot-history). |
| ![Çizim geçmişi düğmeleri](media/plotting-toolbar-04-plot-history-arrows.png) | Önceki/sonraki çizim |  Önceki veya sonraki çizim geçmişinde gider. Ctrl + Alt + F11 (önceki) ve Ctrl + Alt + F12 (İleri) geçmişini de gidebilirsiniz. Bkz: [çizim geçmişi](#plot-history). |
| ![Görüntü Farklı Kaydet düğmesi](media/plotting-toolbar-05-save-as-image.png)| Resim olarak Kaydet | İçin bir dosya adı ister ve geçerli çizim (penceresi içeriği, pencere boyutunu) bir görüntü dosyasına kaydeder. Kullanılabilir biçimleri `.png`, `.jpg`, `.bmp`, ve `.tif`. |
| ![PDF Farklı Kaydet düğmesi](media/plotting-toolbar-06-save-as-pdf.png)| PDF olarak Kaydet | Geçerli çizim geçerli pencere boyutunu kullanarak bir PDF dosyasına kaydeder. PDF ölçeklendirilir varsa çizim yeniden oluşturmaz. |
| ![Bit eşlem düğmesi olarak Kopyala](media/plotting-toolbar-07-copy-as-bitmap.png)| Bit eşlem olarak Kopyala | Çizim panoya geçerli pencere boyutunu kullanarak bir ızgara bitmap olarak kopyalar. | 
| ![Meta dosyası düğmesi olarak Kopyala](media/plotting-toolbar-08-copy-as-metafile.png)| Meta dosyası olarak Kopyala | Panoya olarak çizim kopyalar bir [Windows Meta dosyası](https://en.wikipedia.org/wiki/Windows_Metafile) (Wikipedia). | 
| ![Çizim düğmesini Kaldır](media/plotting-toolbar-09-remove-plot.png)| Çizim Kaldır | Geçerli çizim geçmişinden kaldırır. |
| ![Temizle tüm çizimleri düğmesi](media/plotting-toolbar-10-clear-all-plots.png) | Tüm çizimleri temizleyin | Tüm çizimleri geçmişi (onay ister) kaldırır. |

## <a name="multiple-plot-windows"></a>Birden çok çizim windows

Veri bilimcilerine genellikle birçok farklı veri kümelerindeki birçok çizimleri çalışmak için RTVS sayıda bağımsız çizim windows oluşturmanıza olanak sağlar. Visual Studio çerçevesi içinde veya dışında çerçeve tamamen gibi ancak bu windows sonra düzenleyebilirsiniz. (Bkz [Visual Studio'da pencere düzenlerini özelleştirme](../ide/customizing-window-layouts-in-visual-studio.md) yerleştirme ve windows yeniden boyutlandırma hakkında genel bilgi için.)

Araç çubuğu düğmesini kullanarak yeni bir çizim penceresi oluşturun veya **R Araçlar > çizimleri > Yeni bir çizim pencere**. Yeni bir çizim penceresi hale *etkin* , burada yeni çizimleri işlendiğini olan penceresinin. Etkin pencereyi değiştirmek için geçiş için ve çizim penceresi etkinleştirme araç çubuğu düğmesini seçin veya **R Araçlar > çizer > çizim penceresi etkinleştirme**.

Çizimler, çok, kopyalama veya bunları çizim windows ya da sürükle ve bırak fareyle veya kullanarak kullanarak arasında taşıma anlamına gelir nesneleri bağımsız olan **kopya**, **Kes**, ve **Yapıştır** sağ bağlam komutlarını ve **Düzenle** menüleri.

Sürükle ve bırak için varsayılan davranış kopyasıdır; taşımak için sürükle-Shift tuşunu basılı tutarken bırak.

## <a name="plot-history"></a>Çizim geçmişi

Çizim komutları tüm, bir oturumda Çizdirmek korunur sağlayarak her pencere için çizim geçmişi korunur. Geçmiş gezinmek için ok düğmelerini çizim penceresi araç veya Ctrl + Alt + F11 ve Ctrl + Alt + F12 kullanın. Ayrıca tek çizimleri kaldırın veya araç çubuğu düğmelerini kullanarak yeniden penceresinden tüm çizimleri temizleyin veya **R Araçlar > çizer** menü komutları.

Çizimler koleksiyonunun tamamını görmek için araç çubuğu düğmesini kullanarak çizim Geçmişi penceresini açın veya **R Araçlar > çizer > çizim Geçmişi penceresini**.
Geçmiş farklı çizim windows (veya aygıt) göre gruplandırılan bu penceresinde görüntülenen çizimleri için küçük bir listesi verilmektedir. Araç çubuğundaki Yakınlaştır düğmeleri kullanarak küçük resimlerin boyutunu değiştirir.

![Çizim Geçmiş penceresi](media/plotting-plot-history-window.png)

Bir çizim ilişkili penceresinde açmak için bu çizim çift tıklayın, seçin ve ardından **Göster çizim** araç çubuğu düğmesini veya sağ tıklatın ve seçin **Göster çizim**. Tek bir öğesini de seçebilirsiniz çizim ve kopyalama, kesme veya sağ bağlamdan silin veya **Düzenle** menüleri.

Çizim geçmişinizi tüm pencereleri arasında ömrü etkileşimli R oturumunuz için kullanım ömrü bağlıdır. R oturumunuz sıfırlama veya çıkmak ve Visual Studio'yu yeniden başlatın, çizim geçmişinizi sıfırlanır.

## <a name="programmatically-manipulating-plot-windows"></a>Program aracılığıyla çizim windows düzenleme

Çizim windows R kodundan belirli çizim windows belirlemek için cihazın sayılar kullanılarak programlı olarak yönetebilirsiniz. 

- `dev.list()`: Tüm grafik aygıtları geçerli R oturumunda listeleyin.
- `dev.new()`: Yeni bir grafik cihaz (yeni bir çizim pencere) oluşturun.
- `dev.set(<device number>)`: Etkin grafik aygıtı ayarlayın.
- `dev.off()`: Etkin cihaz silin.
