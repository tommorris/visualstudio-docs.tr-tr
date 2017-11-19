---
title: "Nasıl yapılır: temel bir 3B modeli oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0d97966-2df8-449b-a8cf-5a19684dc773
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4bba90206a428ae9bb782e7eac408b872721351f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-a-basic-3-d-model"></a>Nasıl Yapılır: Temel 3B Model Oluşturma
Bu belge Model Düzenleyicisinde temel 3-b modeli oluşturmak için nasıl kullanılacağını gösterir.  
  
 Bu belgede, bu etkinlikler gösterir:  
  
-   Bir Sahne nesneler ekleme  
  
-   Yüzeyleri ve kenarları seçme  
  
-   Seçimleri çevirme  
  
-   Kullanarak **yüz ayırabilir** ve **yüz Yükselt** araçları  
  
-   Kullanarak **Triangulate** komutu  
  
## <a name="creating-a-basic-3-d-model"></a>Temel 3-b model oluşturma  
 3-b modellere ve oyun veya uygulama için planda oluşturmak ve değiştirmek için Model Düzenleyicisi'ni kullanabilirsiniz. Aşağıdaki adımlar, Model Düzenleyicisinde evin basitleştirilmiş bir 3B model oluşturmak için nasıl kullanılacağını gösterir. Basitleştirilmiş bir model stand-in hala, çakışma algılaması için bir kafes olarak ya da daha ayrıntılı işleme yararlanmaya temsil ettiği nesne çok uzakta olduğunda kullanılacak düşük ayrıntı modeli olarak oluşturulan son resim varlıklar için kullanılabilir.  
  
 İşlemi tamamladığınızda, model aşağıdaki gibi görünmelidir:  
  
 ![Basitleştirilmiş house tamamlanmış modelinin](../designers/media/gfx_model_demo_house_final.png "gfx_model_demo_house_final")  
  
 Başlamadan önce emin olun **özellikleri** penceresi ve **araç** görüntülenir.  
  
#### <a name="to-create-a-simplified-3-d-model-of-a-house"></a>Bir ev Basitleştirilmiş 3-b modeli oluşturmak için  
  
1.  Çalışmak için 3-b bir model oluşturma. Başlarken bölümünde projenize bir model ekleme hakkında daha fazla bilgi için bkz: [Model Düzenleyicisinde](../designers/model-editor.md).  
  
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
  
 Sonraki adım olarak, bu 3-b modeline gölgelendirici uygulayabilirsiniz. Bilgi için bkz: [nasıl yapılır: bir 3B modele gölgelendirici uygulama](../designers/how-to-apply-a-shader-to-a-3-d-model.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Model 3-b Terrain](../designers/how-to-model-3-d-terrain.md)   
 [Model Düzenleyicisi](../designers/model-editor.md)   
 [Gölgelendirici Tasarımcısı](../designers/shader-designer.md)