---
title: 'Nasıl Yapılır: Temel Lambert Gölgelendiricisi Oluşturma'
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: ec5c10fb-9600-4240-8280-d59451ea1d68
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1a843f15275893f0c4ffe110e39bb2069b5a51be
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-create-a-basic-lambert-shader"></a>Nasıl Yapılır: Temel Lambert Gölgelendiricisi Oluşturma

Bu makalede gölgelendirici Tasarımcısı ve yönlendirilmiş grafik gölgelendirici dili (DGSL) Klasik Lambert aydınlatma modeli uygulayan aydınlatma gölgelendirici oluşturmak için nasıl kullanılacağı gösterilmektedir.

## <a name="the-lambert-lighting-model"></a>Lambert aydınlatma modeli

Lambert aydınlatma modeli ortam ve yön aydınlatma 3B Sahne gölge nesneleri için bir araya getirir. Ortam bileşenleri aydınlatma 3B Sahne olarak temel seviyede sağlar. Tek yönlü bileşenleri tek yönlü (Şimdiye kadar koyma) açık kaynaklardan ek aydınlatma sağlar. Ortam aydınlatma Sahne içindeki tüm yüzeyleri eşit, bağımsız olarak kendi yönlendirmesini etkiler. Belirli bir yüzey için ortam yüzey ve rengini renk ve Sahne ortam aydınlatma yoğunluğunu bir üründür. Tek yönlü ışık ışık kaynağının yönüne göre yüzeyini yönünü göre Sahne her yüzey farklı şekilde etkiler. Bu ürün dağıtma renk ve yüzey ve rengi, yoğunluğu ve açık kaynakları yönünü yönünü olur. En fazla katkısı doğrudan ışık kaynağının doğru yüz yüzeyleri alabilir ve doğrudan hemen yüz yüzeyleri hiçbir katkı alırsınız. Lambert aydınlatma modeli altında her nesne noktası toplam dağıtma renk katkı belirlemek için ortam bileşeni ve bir veya daha çok yönlü bileşenleri birleştirilir.

Başlamadan önce emin olun **özellikleri** penceresi ve **araç** görüntülenir.

1.  Çalışmak için DGSL gölgelendirici oluşturun. Başlarken bölümünde DGSL gölgelendirici projenize ekleme hakkında daha fazla bilgi için bkz: [gölgelendirici Tasarımcısı](../designers/shader-designer.md).

2.  Bağlantı kesme **nokta rengi** düğümden **son renk** düğümü. Seçin **RGB** , terminal **nokta rengi** düğümünü ve ardından **bölün bağlantılar**. Bırakın **alfa** terminal bağlı.

3.  Ekleme bir **Lambert** grafiğe düğüm. İçinde **araç**altında **yardımcı programı**seçin **Lambert** ve tasarım yüzeyine taşıyın. Lambert düğüm ortam ve dağıtma aydınlatma parametrelerine göre piksel, toplam dağıtma renk payını hesaplar.

4.  Bağlantı **nokta rengi** düğüme **Lambert** düğümü. İçinde **seçin** modu, taşıma **RGB** , terminal **nokta rengi** düğüme **Dağıt renk** , terminal **Lambert**  düğüm. Bu bağlantı piksel Ara değerli dağıtma rengini lambert düğümle sağlar.

5.  Hesaplanan renk değeri son renk bağlayın. Taşıma **çıkış** , terminal **Lambert** düğüme **RGB** , terminal **son renk** düğümü.

 Aşağıdaki çizimde, grafik ve teapot modeline uygulanan gölgelendirici önizlemesini tamamlanmış gölgelendirici gösterir.

> [!NOTE]
> Bu çizimde gölgelendirici etkisini daha iyi göstermek için turuncu bir renk kullanarak belirtilmiş **MaterialDiffuse** Gölgelendirici parametresi. Oyun veya uygulama bu parametre her nesne için bir benzersiz renk değeri sağlamak için kullanabilirsiniz. Önizleme gölgelendiriciler bölümünde malzeme parametreleri hakkında daha fazla bilgi için bkz [gölgelendirici Tasarımcısı](../designers/shader-designer.md).

 ![Gölgelendirici grafik ve etkisini önizlemesini. ] (../designers/media/digit-lambert-effect-graph.png "Lambert etkisi grafik basamak")

 Belirli şekillerin daha iyi önizlemeleri için bazı gölgelendiriciler sağlayabilir. Önizleme gölgelendiriciler bölümünde gölgelendirici Tasarımcısı'nda gölgelendiriciler önizleme hakkında daha fazla bilgi için bkz [gölgelendirici Tasarımcısı](../designers/shader-designer.md).

 Aşağıdaki çizimde, 3B modeline uygulanan bu belgede açıklanan gölgelendirici gösterir.

 ![Lambert aydınlatma bir modele uygulanır. ] (../designers/media/digit-lambert-effect-result.png "Lambert etkisi sonucu basamak")

 Gölgelendirici uygulama 3B bir modeli hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir 3B modele gölgelendirici uygulama](../designers/how-to-apply-a-shader-to-a-3-d-model.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: bir gölgelendirici 3B bir modeli için geçerlidir](../designers/how-to-apply-a-shader-to-a-3-d-model.md)
- [Nasıl Yapılır: Gölgelendiriciyi Dışarı Aktarma](../designers/how-to-export-a-shader.md)
- [Nasıl Yapılır: Temel Phong Gölgelendiricisi Oluşturma](../designers/how-to-create-a-basic-phong-shader.md)
- [Gölgelendirici Tasarımcısı](../designers/shader-designer.md)
- [Gölgelendirici Tasarımcısı Düğümleri](../designers/shader-designer-nodes.md)