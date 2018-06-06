---
title: 'Nasıl Yapılır: Gri Tonlamalı Doku Gölgelendiricisi Oluşturma'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 79181d81-44af-445e-9a18-03483dd70260
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ef614cbfd611eb9994f378e655d50a8656aa0441
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34746331"
---
# <a name="how-to-create-a-grayscale-texture-shader"></a>Nasıl Yapılır: Gri Tonlamalı Doku Gölgelendiricisi Oluşturma

Bu makalede gölgelendirici Tasarımcısı ve yönlendirilmiş grafik gölgelendirici dili (DGSL) gri tonlamalı doku gölgelendirici oluşturmak için nasıl kullanılacağı gösterilmektedir. Bu gölgelendirici doku örnek RGB renk değerini değiştirir ve sonra son rengini ayarlamak için birlikte değiştirilmemiş alfa değeri kullanır.

## <a name="create-a-grayscale-texture-shader"></a>Gri tonlamalı doku gölgelendiricisi oluşturma

Son çıktı renge yazmadan önce bir doku örnek renk değerini değiştirerek bir gri tonlamalı doku gölgelendirici uygulayabilirsiniz.

Başlamadan önce emin olun **özellikleri** penceresi ve **araç** görüntülenir.

1.  Bölümünde açıklandığı gibi bir temel doku gölgelendirici oluşturma [nasıl yapılır: temel bir doku gölgelendirici oluşturma](../designers/how-to-create-a-basic-texture-shader.md).

2.  Bağlantı kesme **RGB** , terminal **doku örnek** düğümden **RGB** , terminal **son renk** düğümü. İçinde **seçin** modunu seçin **RGB** , terminal **doku örnek** düğümü ve ardından **bölün bağlantılar**. Bu, sonraki adımda eklenen düğüm için yer sağlar.

3.  Ekleme bir **doygunluğunu azaltma** grafiğe düğüm. İçinde **araç**altında **filtreleri**seçin **doygunluğunu azaltma** ve tasarım yüzeyine taşıyın.

4.  Gri tonlamalı değerini kullanarak hesaplamak **doygunluğunu azaltma** düğümü. İçinde **seçin** modu, taşıma **RGB** , terminal **doku örnek** düğüme **RGB** , terminal **doygunluğunu azaltma**  düğüm.

    > [!NOTE]
    > Varsayılan olarak, **doygunluğunu azaltma** düğümü tam olarak giriş rengi desaturates ve standart aydınlatma ağırlıkları gri ölçeği dönüştürme için kullanır. Değiştirebileceğiniz nasıl **doygunluğunu azaltma** düğümü davranır değerini değiştirerek **aydınlatma** özelliği, veya yalnızca kısmen giriş rengi desaturating. Giriş rengi kısmen Doygunluğu Azalt için aralıktaki skaler bir değer sağlamanız [0,1) için **yüzde** , terminal **doygunluğunu azaltma** düğümü.

5.  Gri tonlamalı renk değeri son renk bağlayın. Taşıma **çıkış** , terminal **doygunluğunu azaltma** düğüme **RGB** , terminal **son renk** düğümü.

Aşağıdaki çizimde, grafik ve bir küp uygulanan gölgelendirici önizlemesini tamamlanmış gölgelendirici gösterir.

> [!NOTE]
> Bu çizimde, bir düzlemi Önizleme şekil olarak kullanılır ve bir doku daha iyi gölgelendirici etkisini göstermek için belirtilen.

![Gölgelendirici grafik ve etkisini önizlemesi](../designers/media/digit-grayscale-effect.png)

Belirli şekillerin daha iyi önizlemeleri için bazı gölgelendiriciler sağlayabilir. Gölgelendirici Tasarımcısı'nda gölgelendiriciler önizleme hakkında daha fazla bilgi için bkz: [gölgelendirici Tasarımcısı](../designers/shader-designer.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: bir gölgelendirici 3B bir modeli için geçerlidir](../designers/how-to-apply-a-shader-to-a-3-d-model.md)
- [Nasıl Yapılır: Gölgelendiriciyi Dışarı Aktarma](../designers/how-to-export-a-shader.md)
- [Görüntü Düzenleyicisi](../designers/image-editor.md)
- [Gölgelendirici Tasarımcısı](../designers/shader-designer.md)
- [Gölgelendirici Tasarımcısı Düğümleri](../designers/shader-designer-nodes.md)