---
title: 'Nasıl yapılır: temel bir 3B modeli oluşturma'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: a0d97966-2df8-449b-a8cf-5a19684dc773
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ceeb6bdd5acb878ceb2f3cd6e6e38dada607e1a6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-basic-3d-model"></a>Nasıl yapılır: temel bir 3B modeli oluşturma

Bu makalede, Model Düzenleyicisinde temel 3B model oluşturmak için nasıl kullanılacağı gösterilmektedir. Aşağıdaki etkinlikler ele alınmaktadır:

-   Bir Sahne nesneler ekleme

-   Yüzeyleri ve kenarları seçme

-   Seçimleri çevirme

-   Kullanarak **yüz ayırabilir** ve **yüz Yükselt** araçları

-   Kullanarak **Triangulate** komutu

## <a name="create-a-basic-3d-model"></a>Temel bir 3B modeli oluşturma
 3B modeller ve oyun veya uygulama için planda oluşturmak ve değiştirmek için Model Düzenleyicisi'ni kullanabilirsiniz. Aşağıdaki adımlar, Model Düzenleyicisinde evin Basitleştirilmiş 3B model oluşturmak için nasıl kullanılacağını gösterir. Basitleştirilmiş bir model stand-in hala, çakışma algılaması için bir kafes olarak ya da daha ayrıntılı işleme yararlanmaya temsil ettiği nesne çok uzakta olduğunda kullanılacak düşük ayrıntı modeli olarak oluşturulan son resim varlıklar için kullanılabilir.

 İşlemi tamamladığınızda, model aşağıdaki gibi görünmelidir:

 ![Basitleştirilmiş house tamamlanmış modelinin](../designers/media/gfx_model_demo_house_final.png "gfx_model_demo_house_final")

 Başlamadan önce emin olun **özellikleri** penceresi ve **araç** görüntülenir.

### <a name="to-create-a-simplified-3d-model-of-a-house"></a>Evin basitleştirilmiş bir 3B model oluşturmak için

1.  Çalışmak için 3B bir model oluşturma. Başlarken bölümünde projenize bir model ekleme hakkında daha fazla bilgi için bkz: [Model Düzenleyicisinde](../designers/model-editor.md).

2.  Bir küp için Sahne ekleyin. İçinde **araç** penceresi altında **şekiller**seçin **küp** ve sonra Tasarım yüzeyine taşıyın.

3.  Yüz-seçimi geçin. Model Düzenleyicisi araç çubuğunda seçin **seçin yüz**.

4.  Küpün üstündeki ayırabilir. Yüz seçim modunda seçimini etkinleştirmek için bir kez küp seçin ve en üst yüz seçmek için küp seçin. Model Düzenleyicisi araç çubuğunda seçin **yüz ayırabilir**. Bu, dört eşit boyutta bölümlere bölme küp üstüne yeni köşeleri ekler.

     ![Küpün üstündeki bölünmüştür](../designers/media/gfx_model_demo_house_subdiv.png "gfx_model_demo_house_subdiv")

5.  Küpün iki bitişik kenara Yükselt — Örneğin, ön ve sol tarafında kübün. Yüz seçim modunda küp seçimini etkinleştirmek ve bir tarafındaki küp seçmek için bir kez seçin. Tuşuna basın ve CTRL tuşunu basılı tutun, ilk seçtiğiniz yan bitişik küp başka bir tarafını seçin ve ardından Model Düzenleyicisi araç çubuğunda **yüz Yükselt**.

     ![Küpün yanlarından yükseltilmiş](../designers/media/gfx_model_demo_house_extrude.png "gfx_model_demo_house_extrude")

6.  Extrusions birini genişletin. Yeni yüzeyleri birini yükseltilmiş seçin ve ardından, Model Düzenleyicisi araç çubuğunda **çevir** aracı ve kalıp ile aynı yönde çeviri manipulator taşıyın.

     ![Küpün sütunlardan daha fazla yükseltilmiş. ] (../designers/media/gfx_model_demo_house_extend.png "gfx_model_demo_house_extend")

7.  Model triangulate. Model Düzenleyicisi araç çubuğunda seçin **Gelişmiş**, **Araçları**, **Triangulate**.

8.  Ev tavan oluşturun. Seçerek kenar seçim moduna geç **seçin kenar** Model Düzenleyicisi araç çubuğunda ve etkinleştirmek için küp seçin. Burada gösterilen kenarları seçerken denetim tuşunu basılı tutun:

     ![Tavan yoğun oluşturacak kenarları](../designers/media/gfx_model_demo_house_edges.png "gfx_model_demo_house_edges")

     Kenarları seçildiğinde Model Düzenleyicisi araç çubuğunda seçin **çevir** aracı ve ardından yukarı evin tavan oluşturmak için çeviri manipulator taşıyın.

 Basitleştirilmiş house modeli tamamlanır. İşte son modeli yeniden uygulanan düz gölgelendirme ile:

 ![Basitleştirilmiş house tamamlanmış modelinin](../designers/media/gfx_model_demo_house_final.png "gfx_model_demo_house_final")

 Sonraki adım olarak, bu 3D modele gölgelendirici uygulayabilirsiniz. Bilgi için bkz: [nasıl yapılır: bir 3B modele gölgelendirici uygulama](../designers/how-to-apply-a-shader-to-a-3-d-model.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: Model 3B Terrain](../designers/how-to-model-3-d-terrain.md)
- [Model Düzenleyicisi](../designers/model-editor.md)
- [Gölgelendirici Tasarımcısı](../designers/shader-designer.md)