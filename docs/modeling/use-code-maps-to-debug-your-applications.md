---
title: Uygulamalarınızda hata ayıklamak için kod haritalarını kullanma
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio Ultimate, visualizing code
- Visual Studio Ultimate, navigating code visually
- Visual Studio Ultimate, understanding code
- Visual Studio Ultimate, mapping code relationships
- Visual Studio Ultimate, code maps
- mapping code relationships
- code maps
- mapping relationships in code
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 006db4f3fd820a25b0c413deabce3da5faa70cec
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750278"
---
# <a name="use-code-maps-to-debug-your-applications"></a>Uygulamalarınızda hata ayıklamak için kod haritalarını kullanma
Kod haritaları büyük kod temelleri, tanınmayan kod veya eski kod kayıp önlemenize yardımcı olabilir. Örneğin, hatalarını ayıkladığınız, çok sayıda dosya ve projeleri koduna bakmanız gerekebilir. Kod parçalarını gidin ve aralarındaki ilişkilerin anlamak için kod haritalarını kullanma. Böylece, bu kodu, head, izlemek ya da ayrı bir diyagramı gerekmez. Bu nedenle, çalışmanızı kesintiye uğradığında oluşan kod, bellek, üzerinde çalıştığınız kodu hakkında Yardım yenileme eşler.

 ![Kod Haritası &#45; koddaki ilişkileri eşleme](../modeling/media/codemapstoryboardpaint.png)

 **İmlecinizi Düzenleyicisi'nde göründüğü yeşil ok gösterir**

 Kullanabileceğiniz kod haritalarını ile çalışırken, eylemleri ve komutları ayrıntıları için bkz: [göz atın ve haritalar kod sıralama](../modeling/browse-and-rearrange-code-maps.md).

## <a name="understand-the-problem"></a>Sorunu anlama
 Üzerinde çalıştığınız bir çizim programında bir hata olduğunu varsayın. Hata yeniden oluşturmak için çözümü Visual Studio ve tuşuna açtığınız **F5** hata ayıklama başlatılamıyor.

 Ne zaman bir çizgi çizme ve seçin **my son çizimi geri**, sonraki çizgi çizme kadar hiçbir şey olmaz.

 ![Kod Haritası &#45; yeniden oluşturma hatası](../modeling/media/codemapstoryboardpaint0.png)

 İçin arama yaparak araştırma başlatmak için `Undo` yöntemi. İçinde bulma `PaintCanvas` sınıfı.

 ![Kod Haritası &#45; kod Bul](../modeling/media/codemapstoryboardpaint1.png)

## <a name="start-mapping-the-code"></a>Kodu eşleştirmeyi başlat
 Eşleme işlemini şimdi başlatabilir `undo` yöntemi ve ilişkileri. Kod Düzenleyicisi'nden eklediğiniz `undo` yöntemi ve yeni bir kod Haritası başvurduğu alanları. Yeni bir eşleme oluşturduğunuzda, kodun dizinini oluşturmak biraz zaman alabilir. Bu, sonraki işlemlerin daha hızlı çalışmasını sağlar.

 ![Kod Haritası &#45; yöntemi ve ilgili alanları göster](../modeling/media/codemapstoryboardpaint3.png)

> [!TIP]
>  Yeşil vurgu eşlemeye eklenen son öğeleri gösterir. Yeşil ok kodda, imlecin konumunu gösterir. Öğeler arasındaki oklar farklı ilişkileri temsil eder. Fare üzerlerine taşıma ve bunların araç ipuçları inceleyerek haritada öğeleri hakkında daha fazla bilgi alabilirsiniz.

 ![Kod Haritası &#45; araç ipuçlarını göster](../modeling/media/codemapstoryboardpaint4.png)

## <a name="navigate-and-examine-code-from-the-map"></a>Eşlemeden koda gitme ve kodu inceleme
 Her bir alan için kod tanımı görmek için harita üzerinde alanı çift tıklatın veya alanı seçip tuşuna **F12**. Yeşil ok eşlemedeki öğeler arasında hareket eder. Ayrıca kod düzenleyicisindeki imleciniz de otomatik olarak hareket eder.

 ![Kod Haritası &#45; alan tanımı inceleyin](../modeling/media/codemapstoryboardpaint5.png)

 ![Kod Haritası &#45; alan tanımı inceleyin](../modeling/media/codemapstoryboardpaint5a.png)

> [!TIP]
>  Kod düzenleyicisinde imleci hareket ettirerek yeşil oku eşlemede taşıyabilirsiniz.

## <a name="understand-relationships-between-pieces-of-code"></a>Kod parçaları arasındaki ilişkileri anlama
 Başka bir kod bilmek ister artık etkileşime `history` ve `paintObjects` alanları. Bu alanlara başvuran tüm yöntemleri eşlemeye ekleyebilirsiniz. Harita veya Kod düzenleyicisinde bunu yapabilirsiniz.

 ![Kod Haritası &#45; tüm başvuruları Bul](../modeling/media/codemapstoryboardpaint6.png)

 ![Kod Düzenleyicisi'nden bir kod Haritası açın](../modeling/media/codemapstoryboardpaint6a.png)

> [!NOTE]
>  Daha sonra Windows Phone veya Windows mağazası, gibi birden çok uygulama arasında paylaşılan bir projeden öğeleri eklerseniz, bu öğeler harita üzerinde şu anda etkin uygulama projesi ile olmadığını her zaman görünür. Harita üzerinde bağlamı için de değişir sonra başka bir uygulama projesine bağlam değiştirirseniz, bu nedenle, yeni öğeleri paylaşılan projeden eklenen tüm. Eşleme üzerinde bir öğeyle gerçekleştirdiğiniz işlemler, yalnızca aynı bağlamı paylaşılan öğeler için geçerlidir.

 İlişkilerin akışını yeniden düzenlemek ve eşlemenin okunmasını kolaylaştırmak için düzeni değiştirin. Ayrıca, öğeleri sürükleyerek de eşleme etrafında taşıyabilirsiniz.

 ![Kod Haritası &#45; Düzeni Değiştir](../modeling/media/codemapstoryboardpaint7a.png)

> [!TIP]
>  Varsayılan olarak, **artan düzen** açıktır. Yeni öğeler eklediğinizde, bu eşlemeyi mümkün olduğunca az yeniden düzenler. Yeni öğeler eklemek her zaman tüm harita yeniden düzenlemek için kapatmak **artan düzen**.

 ![Kod Haritası &#45; Düzeni Değiştir](../modeling/media/codemapstoryboardpaint7.png)

 Bu yöntemleri inceleyelim. Harita üzerinde çift tıklatın **PaintCanvas** yöntemi, ya da bu yöntemi seçip tuşuna **F12**. Bu yöntem oluşturduğu öğrenin `history` ve `paintObjects` boş liste olarak.

 ![Kod Haritası &#45; yöntemi tanımı inceleyin](../modeling/media/codemapstoryboardpaint8.png)

 Şimdi incelemek için aynı adımları yineleyin `clear` yöntemi tanımı. Bu bilgi `clear` ile bazı görevleri gerçekleştirir `paintObjects` ve `history`. Daha sonra çağırır `Repaint` yöntemi.

 ![Kod Haritası &#45; yöntemi tanımı inceleyin](../modeling/media/codemapstoryboardpaint9.png)

 Şimdi incelemek `addPaintObject` yöntemi tanımı. Ayrıca bazı görevleri gerçekleştirir `history` ve `paintObjects`. Ayrıca çağırır `Repaint`.

 ![Kod Haritası &#45; yöntemi tanımı inceleyin](../modeling/media/codemapstoryboardpaint10.png)

## <a name="find-the-problem-by-examining-the-map"></a>Eşlemeyi inceleyerek sorunu bulma
 Tüm yöntemleri değiştirmek gibi görünüyor `history` ve `paintObjects` çağrı `Repaint`. Henüz `undo` değil yöntemini çağırın `Repaint`rağmen `undo` aynı alanları değiştirir. Çağırarak bu sorunu düzeltebileceğiniz düşündüğünüz şekilde `Repaint` gelen `undo`.

 ![Kod Haritası &#45; yöntem çağrısı eksik Bul](../modeling/media/codemapstoryboardpaint11.png)

 Size bu eksik çağrıyı gösteren bir eşlemeniz yoksa, özellikle de daha karmaşık kod söz konusu olduğunda bu sorunun bulunması daha zor olabilir.

## <a name="share-your-discovery-and-next-steps"></a>Keşfinizi ve sonraki adımları paylaşma
 Siz veya başka biri bu hatayı düzeltmeden önce, eşlemenin üzerine sorunla ve bu sorunun düzeltilmesiyle ilgili notlar ekleyebilirsiniz.

 ![Kod Haritası &#45; izleme için açıklama ve bayrağı öğeleri](../modeling/media/codemapstoryboardpaint12.png)

 Örneğin, eşlemeye açıklamalar ekleyebilir ve renkler kullanarak öğeleri işaretleyebilirsiniz.

 ![Kod Haritası &#45; açıklamalı ve bayraklı öğeler](../modeling/media/codemapstoryboardpaint12a.png)

 Microsoft Outlook yüklüyse, eşlemeyi başkalarına e-postayla gönderebilirsiniz. Eşlemeyi bir görüntü veya başka bir biçim olarak dışarı da aktarabilirsiniz.

 ![Kod Haritası &#45; paylaşımı, verme, posta](../modeling/media/codemapstoryboardpaint13.png)

## <a name="fix-the-problem-and-show-what-you-did"></a>Sorunu giderme ve ne yaptığınızı gösterme
 Bu hatayı gidermek için çağrısı ekleyin `Repaint` için `undo`.

 ![Kod Haritası &#45; eksik yöntemi çağrısı ekleyin](../modeling/media/codemapstoryboardpaint14.png)

 Düzeltmenizi onaylamak için hata ayıklama oturumunu yeniden başlatır ve hatayı yeniden oluşturmaya çalışırsınız. Şimdi seçme **my son çizimi geri** beklediğiniz gibi çalıştığından ve doğru düzeltme yaptığınız onaylar.

 ![Kod Haritası &#45; Onayla kod düzeltme](../modeling/media/codemapstoryboardpaint15.png)

 Eşlemeyi yaptığınız düzeltmeyi gösterecek şekilde güncelleştirebilirsiniz.

 ![Kod Haritası &#45; yöntem çağrısı eksik olan güncelleştirme eşlemesi](../modeling/media/codemapstoryboardpaint16.png)

 Haritanızı şimdi arasında bir bağlantı gösterir **geri** ve **yeniden boyamak**.

 ![Kod Haritası &#45; yöntem çağrısı güncelleştirilmiş Haritası](../modeling/media/codemapstoryboardpaint17.png)

> [!NOTE]
>  Eşlemeyi güncelleştirdiğinizde, eşlemeyi oluşturmak için kullanılan kod dizininin güncelleştirdiğini belirten bir ileti görebilirsiniz. Bu, birisinin kodu eşlemenizin geçerli kodla eşleşmemesine neden olacak şekilde değiştirdiği anlamına gelir. Bu sizi eşlemeyi güncelleştirmekten alıkoymaz, ancak kodla eşleştiğini doğrulamak için eşlemeyi yeniden oluşturmak zorunda kalabilirsiniz.

 Şimdi araştırmanızı ile işiniz bittiğinde. Kodu eşleştirerek sorunu başarıyla buldunuz ve giderdiniz. Ayrıca kodda gezinmeye ve öğrendiklerinizi hatırlamanıza yardımcı olan ve sorunu gidermek için attığınız adımları gösteren bir eşlemeniz de vardır.

## <a name="see-also"></a>Ayrıca Bkz.

- [Hata ayıklarken çağrı yığınında yöntemler eşleştirme](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)
- [Kodu görselleştirme](../modeling/visualize-code.md)
