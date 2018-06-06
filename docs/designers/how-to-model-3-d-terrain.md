---
title: 'Nasıl yapılır: Model 3B Terrain'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: f779b1fd-82a9-4a11-8ab7-c1c9caabc883
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b62ad2d954435e5556f2f427d531d806dfb7be18
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745584"
---
# <a name="how-to-model-3d-terrain"></a>Nasıl yapılır: Model 3B Terrain

Bu makalede, Model Düzenleyicisinde bir 3B terrain model oluşturmak için nasıl kullanılacağı gösterilmektedir.

## <a name="create-a-3d-terrain-model"></a>Bir 3B terrain modeli oluşturma

Bir 3B terrain ek yüzeyleri yapmak için bir düzlemi kümelere bölme ve ilginç terrain özellikleri oluşturmak için kendi köşeleri düzenleme oluşturabilirsiniz.

İşlemi tamamladığınızda, model aşağıdaki gibi görünmelidir:

![3&#45;terrain modelini gösteren D Sahne](../designers/media/digit-terrain-model.png)

Başlamadan önce emin olun **özellikleri** penceresi ve **araç** görüntülenir.

1.  Çalışmak için 3B bir model oluşturma. Başlarken bölümünde projenize bir model ekleme hakkında daha fazla bilgi için bkz: [Model Düzenleyicisinde](../designers/model-editor.md).

2.  Bir düzlemi Sahne ekleyin. İçinde **araç**altında **şekiller**seçin **düzlemi** ve tasarım yüzeyine taşıyın.

    > [!TIP]
    > Düzlemi nesne çalışmak daha kolay hale getirmek için tasarım yüzeyine çerçevesi. İçinde **seçin** modu, Düzlemi nesne seçin ve ardından Model Düzenleyicisi araç çubuğunda belirtin **çerçeve nesnesi** düğmesi.

3.  Yüz seçim modunu girin. Model Düzenleyicisi araç çubuğunda seçin **seçin yüz**.

4.  Düzlemi ayırabilir. Yüz seçim modunda seçimini etkinleştirmek için düzlemi bir kez seçin ve sonra yalnızca yüz yeniden seçmek için seçin. Model Düzenleyicisi araç çubuğunda seçin **yüz ayırabilir**. Bu yeni köşeleri dört eşit boyutta bölümlere bölme düzlemi ekler.

5.  Daha fazla alt bölüm oluşturun. Yeni yüzeyleri seçiliyken seçin **yüz ayırabilir** iki kez daha. Bu, 64 yüzeyleri toplam oluşturur. Daha fazla alt bölüm oluşturarak terrain daha fazla ayrıntı verebilir.

6.  Seçim modu noktası girin. Model Düzenleyicisi araç çubuğunda seçin **seçin noktası**.

7.  Terrain özelliği oluşturmak için bir noktayı değiştirin. Noktası seçim modunda noktalarından birini seçin ve Model Düzenleyicisi araç çubuğunda seçin **çevir** aracı. Noktayı gösteren bir kutusu tasarım yüzeyine görüntülenir. Yeşil ok kutusuna gidin ve böylece noktası yüksekliğini değiştirmek için kullanın. İlginç terrain özellikleri oluşturmak farklı noktaları için bu adımı yineleyin.

    > [!TIP]
    > Aynı anda tek bir yolla değiştirmek için çeşitli noktalar seçebilirsiniz.

Tam terrain modelidir. İşte son modeli yeniden uygulanan Phong gölgelendirme ile:

![3&#45;terrain modelini gösteren D Sahne](../designers/media/digit-terrain-model.png)

Açıklanan gradyan gölgelendirici etkisini göstermek için bu terrain modelini kullanabilirsiniz [nasıl yapılır: bir geometri tabanlı gradyan gölgelendirici oluşturma](../designers/how-to-create-a-geometry-based-gradient-shader.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Model Düzenleyicisi](../designers/model-editor.md)