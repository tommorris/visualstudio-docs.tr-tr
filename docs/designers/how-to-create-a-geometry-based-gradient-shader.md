---
title: 'Nasıl yapılır: geometri tabanlı gradyan gölgelendirici oluşturun | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
ms.assetid: 4b204405-ba95-4c5e-bd51-ec033a3ebfb6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6ec140a434ebee19eb64292d38216d567a60d8bc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-geometry-based-gradient-shader"></a>Nasıl Yapılır: Geometri Tabanlı Gradyan Gölgelendirici Oluşturma
Bu belgede gölgelendirici Tasarımcısı ve yönlendirilmiş grafik gölgelendirici dili geometri tabanlı gradyan gölgelendirici oluşturmak için nasıl kullanılacağı gösterilmektedir. Bu gölgelendirici sabit bir RGB rengi değer yüksekliğini dünya uzayındaki nesnenin her bir noktanın göre ölçeklendirir.  
  
 Bu belgede, bu etkinlikler gösterir:  
  
-   Gölgelendirici grafiğe düğüm ekleme  
  
-   Düğüm özelliklerini ayarlama  
  
-   Düğümleri bağlantısı kesiliyor  
  
-   Düğümlerini bağlayan  
  
## <a name="creating-a-geometry-based-gradient-shader"></a>Geometri tabanlı gradyan gölgelendirici oluşturma  
 Piksel konumunu, gölgelendirici ekleme tarafından geometri tabanlı gölgelendirici uygulayabilirsiniz. Gölgeleme dillerde piksel 2B ekranda yalnızca kendi renk ve konum daha fazla bilgi içerir. Bir piksel — olarak bilinen bir *parça* bazı sistemlerinde — karşılık gelen bir piksel yüzeye açıklamak değerleri koleksiyonudur. Bu belgede açıklanan gölgelendirici her pikselini world alanda parça son çıktı rengini etkilemek için 3B bir nesnenin yüksekliğini kullanır.  
  
 Başlamadan önce emin olun **özellikleri** penceresi ve **araç** görüntülenir.  
  
#### <a name="to-create-a-geometry-based-gradient-shader"></a>Geometri tabanlı gradyan gölgelendirici oluşturmak için  
  
1.  Çalışmak için DGSL gölgelendirici oluşturun. Başlarken bölümünde DGSL gölgelendirici projenize ekleme hakkında daha fazla bilgi için bkz: [gölgelendirici Tasarımcısı](../designers/shader-designer.md).  
  
2.  Bağlantı kesme **nokta rengi** düğümden **son renk** düğümü. Seçin **RGB** , terminal **nokta rengi** düğümünü ve ardından **bölün bağlantılar**. Bu, sonraki adımda eklenen düğüm için yer sağlar.  
  
3.  Ekleme bir **Çarp** grafiğe düğüm. İçinde **araç**altında **matematik**seçin **Çarp** ve tasarım yüzeyine taşıyın.  
  
4.  Ekleme bir **maskesi vektör** grafiğe düğüm. İçinde **araç**altında **yardımcı programı**seçin **maskesi vektör** ve tasarım yüzeyine taşıyın.  
  
5.  Maskesi değerlerini belirtin **maskesi vektör** düğümü. İçinde **seçin** modunu seçin **maskesi vektör** düğümünü ve ardından **özellikleri** penceresindeki ayarlayın **yeşil / Y** özelliğine**True**ve ardından **kırmızı / X**, **mavi / Z** ve **alfa / W** özelliklerine **False**. Bu örnekte, **kırmızı / X**, **yeşil / Y**, ve **mavi / Z** özellikleri karşılık x, y ve z bileşenlerini **World konumu** düğüm, ve **alfa / W** kullanılmıyor. Çünkü yalnızca **yeşil / Y** ayarlanır **doğru**, yalnızca giriş vektör y bileşeni, maskelenmiş sonra kalır.  
  
6.  Ekleme bir **World konumu** grafiğe düğüm. İçinde **araç**altında **sabitleri**seçin **World konumu** ve tasarım yüzeyine taşıyın.  
  
7.  Parça world alanı konumunu maske. İçinde **seçin** modu, taşıma **çıkış** , terminal **World konumu** düğüme **vektör** , terminal **maskesi Vektör** düğümü. Bu bağlantı x ve z yoksaymak için parça konumunu maskeleri bileşenleri.  
  
8.  RGB renk sabiti maskelenmiş world alanı konumuna göre çarpın. Taşıma **RGB** , terminal **nokta rengi** düğüme **Y** , terminal **Çarp** düğümünü ve ardından taşıyın  **Çıktı** , terminal **maskesi vektör** düğüme **X** , terminal **Çarp** düğümü. Bu bağlantı, dünya uzayındaki piksel yüksekliğini tarafından renk değeri ölçeklendirir.  
  
9. Ölçeklendirilmiş renk değeri son renk bağlayın. Taşıma **çıkış** , terminal **Çarp** düğüme **RGB** , terminal **son renk** düğümü.  
  
 Aşağıdaki çizimde, grafik ve bir küre uygulanan gölgelendirici önizlemesini tamamlanmış gölgelendirici gösterir.  
  
> [!NOTE]
>  Bu çizimde, daha iyi gölgelendirici etkisini göstermek için turuncu bir renk belirtildi, ancak Önizleme şekli world alanı hiçbir konumda bulunduğundan, gölgelendirici tam olarak gölgelendirici Tasarımcısı'nda önizlemesi yapılamıyor. Gölgelendirici tam etkisi göstermek için gerçek Sahne önizlemesi gerekir.  
  
 ![Gölgelendirici grafik ve etkisini önizlemesini](../designers/media/digit-gradient-effect-graph.png "basamaklı gradyan etkisi grafiği")  
  
 Belirli şekillerin daha iyi önizlemeleri için bazı gölgelendiriciler sağlayabilir. Gölgelendirici Tasarımcısı'nda gölgelendiriciler önizleme hakkında daha fazla bilgi için bkz: **gölgelendiriciler Önizleme** içinde [gölgelendirici Tasarımcısı](../designers/shader-designer.md)  
  
 Örneklerde gösterildiği 3B Sahne uygulanan bu belgede açıklanan gölgelendirici aşağıda gösterilmiştir [nasıl yapılır: Model 3-b Terrain](../designers/how-to-model-3-d-terrain.md). Yüksekliğini dünya noktanın ile Rengin yoğunluğunu artırır.  
  
 ![3'e uygulanan gradyan efektinin&#45;D terrain modeli](../designers/media/digit-gradient-effect-result.png "basamaklı gradyan etkisi sonucu")  
  
 3B modele gölgelendirici uygulama hakkında daha fazla bilgi için bkz: [nasıl yapılır: Gölgelendirici uygulama 3B modele](../designers/how-to-apply-a-shader-to-a-3-d-model.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir 3B modele gölgelendirici uygulama](../designers/how-to-apply-a-shader-to-a-3-d-model.md)   
 [Nasıl yapılır: bir gölgelendirici dışarı aktarma](../designers/how-to-export-a-shader.md)   
 [Nasıl yapılır: Model 3-b Terrain](../designers/how-to-model-3-d-terrain.md)   
 [Nasıl yapılır: bir gri tonlamalı doku gölgelendirici oluşturma](../designers/how-to-create-a-grayscale-texture-shader.md)   
 [Gölgelendirici Tasarımcısı](../designers/shader-designer.md)   
 [Gölgelendirici Tasarımcısı Düğümleri](../designers/shader-designer-nodes.md)