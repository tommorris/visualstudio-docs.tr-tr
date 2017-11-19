---
title: "Nasıl yapılır: bir temel Phong gölgelendirici oluşturun | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7c69da8-142b-4d3b-9be9-4be0d5970b25
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 29def0d3aef8a097f5b956bd43df7d8b53abebb9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-a-basic-phong-shader"></a>Nasıl Yapılır: Temel Phong Gölgelendiricisi Oluşturma
Bu belgede gölgelendirici Tasarımcısı ve yönlendirilmiş grafik gölgelendirici dili (DGSL) Klasik Phong aydınlatma modeli uygulayan aydınlatma gölgelendirici oluşturmak için nasıl kullanılacağı gösterilmektedir.  
  
 Bu belgede, bu etkinlikler gösterir:  
  
-   Gölgelendirici grafiğe düğüm ekleme  
  
-   Düğümleri bağlantısı kesiliyor  
  
-   Düğümlerini bağlayan  
  
## <a name="the-phong-lighting-model"></a>Phong aydınlatma modeli  
 Phong aydınlatma modelini, yansıtıcı bir yüzey özelliklerini benzetim aynasal vurgulama, dahil etmek için Lambert aydınlatma modeli genişletir. Ek aydınlatma Lambert aydınlatma modelinde kullanılan aynı kaynaktan tek yönlü hafif aynasal bileşeni sağlar, ancak son renk kendi katkısı farklı şekilde işlenir. Aynasal vurgulama Sahne her yüzey farklı şekilde, görünüm yönü, hafif kaynakları yönünü ve yüzey yönünü arasındaki ilişkiyi göre etkiler. Aynasal rengi, aynasal güç ve yüzey ve rengi, yoğunluğu ve açık kaynakları yönünü yönünü bir üründür. En fazla aynasal katkı doğrudan Görüntüleyici hafif kaynakta yansıtacak yüzeyleri almak ve hiçbir katkı Görüntüleyici çıktığınızda ışık kaynağının yansıtacak yüzeyleri alabilirsiniz. Phong aydınlatma modeli altında bir veya daha fazla aynasal bileşenleri renk ve her nesne noktası aynasal vurgulamanın yoğunluğu belirlemek için birleştirilir ve ardından piksel son rengi üretmek için Lambert aydınlatma modeli sonucuna eklenir .  
  
 Lambert aydınlatma modeli hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir temel Lambert gölgelendirici oluşturma](../designers/how-to-create-a-basic-lambert-shader.md).  
  
 Başlamadan önce emin olun **özellikleri** penceresi ve **araç** görüntülenir.  
  
#### <a name="to-create-a-phong-shader"></a>Phong gölgelendirici oluşturmak için  
  
1.  Lambert gölgelendirici açıklandığı gibi oluşturmak [nasıl yapılır: bir temel Lambert gölgelendirici oluşturma](../designers/how-to-create-a-basic-lambert-shader.md).  
  
2.  Bağlantı kesme **Lambert** düğümden **son renk** düğümü. Seçin **RGB** , terminal **Lambert** düğümünü ve ardından **bölün bağlantılar**. Bu, sonraki adımda eklenen düğüm için yer sağlar.  
  
3.  Ekle bir **Ekle** grafiğe düğüm. İçinde **araç**altında **matematik**seçin **Ekle** ve tasarım yüzeyine taşıyın.  
  
4.  Ekleme bir **Specular** grafiğe düğüm. İçinde **araç**altında **yardımcı programı**seçin **Specular** ve tasarım yüzeyine taşıyın.  
  
5.  Aynasal katkı ekleyin. Taşıma **çıkış** , terminal **Specular** düğüme **X** , terminal **Ekle** düğümünü ve ardından taşıyın **çıkış**  , terminal **Lambert** düğüme **Y** , terminal **Ekle** düğümü. Bu bağlantılar piksel toplam dağıtma ve aynasal renk Katkıları birleştirin.  
  
6.  Hesaplanan renk değeri son renk bağlayın. Taşıma **çıkış** , terminal **Ekle** düğüme **RGB** , terminal **son renk** düğümü.  
  
 Aşağıdaki çizimde, grafik ve teapot modeline uygulanan gölgelendirici önizlemesini tamamlanmış gölgelendirici gösterir.  
  
> [!NOTE]
>  Bu çizimde gölgelendirici etkisini daha iyi göstermek için turuncu bir renk kullanarak belirtilmiş **MaterialDiffuse** kullanarakgölgelendiricivemetalikgörünümlübirbitişparametresibelirtilmedi**MaterialSpecular** ve **MaterialSpecularPower** parametreleri. Önizleme gölgelendiriciler bölümünde malzeme parametreleri hakkında daha fazla bilgi için bkz [gölgelendirici Tasarımcısı](../designers/shader-designer.md).  
  
 ![Gölgelendirici grafik ve etkisini önizlemesini](../designers/media/digit-lighting-graph.png "basamaklı aydınlatma grafiği")  
  
 Belirli şekillerin daha iyi önizlemeleri için bazı gölgelendiriciler sağlayabilir. Önizleme gölgelendiriciler bölümünde gölgelendirici Tasarımcısı'nda gölgelendiriciler önizleme hakkında daha fazla bilgi için bkz [gölgelendirici Tasarımcısı](../designers/shader-designer.md)  
  
 Aşağıdaki çizimde, 3-b modeline uygulanan bu belgede açıklanan gölgelendirici gösterir. **MaterialSpecular** özelliği ayarlanmış (1.00, 0,50, 0,20, 0,00) ve kendi **MaterialSpecularPower** özelliği, 16 olarak ayarlanır.  
  
> [!NOTE]
>  **MaterialSpecular** özelliği yüzey malzeme görünen bitiş belirler. Acil Durum ya da plastik gibi yüksek çalışma yüzeyi beyaz açık gölgeye olan aynasal renk sahip eğilimindedir. Metalik yüzeyini dağıtma rengini yakın olan aynasal renk sahip eğilimindedir. Saten bitiş yüzeyini gri koyu gölgeye olan aynasal renk sahip eğilimindedir.  
>   
>  **MaterialSpecularPower** özelliği, aynasal vurgular nasıl yoğun olan belirler. Yüksek aynasal powers düzeyi benzetimini, daha fazla yerelleştirilmiş vurgular. Çok düşük aynasal powers oversaturate ve tüm yüzeyini rengini Gizle yoğun, sakınımlı vurgular benzetimi.  
  
 ![Bir modeline uygulanan Phong aydınlatma](../designers/media/digit-lighting-model.png "basamaklı aydınlatma modeli")  
  
 3B modele gölgelendirici uygulama hakkında daha fazla bilgi için bkz: [nasıl yapılır: Gölgelendirici uygulama 3B modele](../designers/how-to-apply-a-shader-to-a-3-d-model.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir 3B modele gölgelendirici uygulama](../designers/how-to-apply-a-shader-to-a-3-d-model.md)   
 [Nasıl yapılır: bir gölgelendirici dışarı aktarma](../designers/how-to-export-a-shader.md)   
 [Nasıl yapılır: bir temel Lambert gölgelendirici oluşturma](../designers/how-to-create-a-basic-lambert-shader.md)   
 [Gölgelendirici Tasarımcısı](../designers/shader-designer.md)   
 [Gölgelendirici Tasarımcı düğümler](../designers/shader-designer-nodes.md)