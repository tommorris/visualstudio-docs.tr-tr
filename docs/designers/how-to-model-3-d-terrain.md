---
title: "Nasıl yapılır: Model 3-b Terrain | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f779b1fd-82a9-4a11-8ab7-c1c9caabc883
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: cccd65c62d8b5a0f75052c3121e313507ad5d8b8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-model-3-d-terrain"></a>Nasıl Yapılır: Model 3B Arazi
Bu belge Model Düzenleyicisinde 3-b terrain modeli oluşturmak için nasıl kullanılacağını gösterir.  
  
 Bu belgede, bu etkinlikler gösterir:  
  
-   Bir Sahne nesneler ekleme  
  
-   Yazıtipleri ve noktaları seçme  
  
-   Seçimleri çevirme  
  
-   Kullanarak **yüz ayırabilir** aracı  
  
-   Bir tasarım yüzeyine nesnesinde çerçeveleme  
  
## <a name="creating-a-3-d-terrain-model"></a>3-b terrain model oluşturma  
 Ek yüzeyleri yapmak için bir düzlemi kümelere bölme ve ilginç terrain özellikleri oluşturmak için kendi köşeleri düzenleme 3-b terrain oluşturabilirsiniz.  
  
 İşlemi tamamladığınızda, model aşağıdaki gibi görünmelidir:  
  
 ![3 &#45; terrain modelini gösteren D Sahne](../designers/media/digit-terrain-model.png "basamaklı Terrain modeli")  
  
 Başlamadan önce emin olun **özellikleri** penceresi ve **araç** görüntülenir.  
  
#### <a name="to-create-a-3-d-terrain-model"></a>Bir 3B terrain model oluşturmak için  
  
1.  Çalışmak için 3-b bir model oluşturma. Başlarken bölümünde projenize bir model ekleme hakkında daha fazla bilgi için bkz: [Model Düzenleyicisinde](../designers/model-editor.md).  
  
2.  Bir düzlemi Sahne ekleyin. İçinde **araç**altında **şekiller**seçin **düzlemi** ve tasarım yüzeyine taşıyın.  
  
    > [!TIP]
    >  Düzlemi nesne çalışmak daha kolay hale getirmek için tasarım yüzeyine çerçevesi. İçinde **seçin** modu, Düzlemi nesne seçin ve ardından Model Düzenleyicisi araç çubuğunda belirtin **çerçeve nesnesi** düğmesi.  
  
3.  Yüz seçim modunu girin. Model Düzenleyicisi araç çubuğunda seçin **seçin yüz**.  
  
4.  Düzlemi ayırabilir. Yüz seçim modunda seçimini etkinleştirmek için düzlemi bir kez seçin ve sonra yalnızca yüz yeniden seçmek için seçin. Model Düzenleyicisi araç çubuğunda seçin **yüz ayırabilir**. Bu yeni köşeleri dört eşit boyutta bölümlere bölme düzlemi ekler.  
  
5.  Daha fazla alt bölüm oluşturun. Yeni yüzeyleri seçiliyken seçin **yüz ayırabilir** iki kez daha. Bu, 64 yüzeyleri toplam oluşturur. Daha fazla alt bölüm oluşturarak terrain daha fazla ayrıntı verebilir.  
  
6.  Seçim modu noktası girin. Model Düzenleyicisi araç çubuğunda seçin **seçin noktası**.  
  
7.  Terrain özelliği oluşturmak için bir noktayı değiştirin. Noktası seçim modunda noktalarından birini seçin ve Model Düzenleyicisi araç çubuğunda seçin **çevir** aracı. Noktayı gösteren bir kutusu tasarım yüzeyine görüntülenir. Yeşil ok kutusuna gidin ve böylece noktası yüksekliğini değiştirmek için kullanın. İlginç terrain özellikleri oluşturmak farklı noktaları için bu adımı yineleyin.  
  
    > [!TIP]
    >  Aynı anda tek bir yolla değiştirmek için çeşitli noktalar seçebilirsiniz.  
  
 Tam terrain modelidir. İşte son modeli yeniden uygulanan Phong gölgelendirme ile:  
  
 ![3 &#45; terrain modelini gösteren D Sahne](../designers/media/digit-terrain-model.png "basamaklı Terrain modeli")  
  
 Açıklanan gradyan gölgelendirici etkisini göstermek için bu terrain modelini kullanabilirsiniz [nasıl yapılır: bir geometri tabanlı gradyan gölgelendirici oluşturma](../designers/how-to-create-a-geometry-based-gradient-shader.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Model Düzenleyicisi](../designers/model-editor.md)