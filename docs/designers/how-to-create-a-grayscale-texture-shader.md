---
title: "Nasıl yapılır: bir gri tonlamalı doku gölgelendirici oluşturun | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 79181d81-44af-445e-9a18-03483dd70260
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 515aefab86a0a047d7074d127d9dd621feb0117c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-grayscale-texture-shader"></a>Nasıl Yapılır: Gri Tonlamalı Doku Gölgelendiricisi Oluşturma
Bu belgede gölgelendirici Tasarımcısı ve yönlendirilmiş grafik gölgelendirici dili (DGSL) gri tonlamalı doku gölgelendirici oluşturmak için nasıl kullanılacağı gösterilmektedir. Bu gölgelendirici doku örnek RGB renk değerini değiştirir ve sonra son rengini ayarlamak için birlikte değiştirilmemiş alfa değeri kullanır.  
  
## <a name="creating-a-grayscale-texture-shader"></a>Gri tonlamalı doku gölgelendirici oluşturma  
 Son çıktı renge yazmadan önce bir doku örnek renk değerini değiştirerek bir gri tonlamalı doku gölgelendirici uygulayabilirsiniz.  
  
 Başlamadan önce emin olun **özellikleri** penceresi ve **araç** görüntülenir.  
  
#### <a name="to-create-a-grayscale-texture-shader"></a>Gri tonlamalı doku gölgelendirici oluşturmak için  
  
1.  Bölümünde açıklandığı gibi bir temel doku gölgelendirici oluşturma [nasıl yapılır: temel bir doku gölgelendirici oluşturma](../designers/how-to-create-a-basic-texture-shader.md).  
  
2.  Bağlantı kesme **RGB** , terminal **doku örnek** düğümden **RGB** , terminal **son renk** düğümü. İçinde **seçin** modunu seçin **RGB** , terminal **doku örnek** düğümü ve ardından **bölün bağlantılar**. Bu, sonraki adımda eklenen düğüm için yer sağlar.  
  
3.  Ekleme bir **doygunluğunu azaltma** grafiğe düğüm. İçinde **araç**altında **filtreleri**seçin **doygunluğunu azaltma** ve tasarım yüzeyine taşıyın.  
  
4.  Gri tonlamalı değerini kullanarak hesaplamak **doygunluğunu azaltma** düğümü. İçinde **seçin** modu, taşıma **RGB** , terminal **doku örnek** düğüme **RGB** , terminal **doygunluğunu azaltma**  düğüm.  
  
    > [!NOTE]
    >  Varsayılan olarak, **doygunluğunu azaltma** düğümü tam olarak giriş rengi desaturates ve standart aydınlatma ağırlıkları gri ölçeği dönüştürme için kullanır. Değiştirebileceğiniz nasıl **doygunluğunu azaltma** düğümü davranır değerini değiştirerek **aydınlatma** özelliği, veya yalnızca kısmen giriş rengi desaturating. Giriş rengi kısmen Doygunluğu Azalt için aralıktaki skaler bir değer sağlamanız [0,1) için **yüzde** , terminal **doygunluğunu azaltma** düğümü.  
  
5.  Gri tonlamalı renk değeri son renk bağlayın. Taşıma **çıkış** , terminal **doygunluğunu azaltma** düğüme **RGB** , terminal **son renk** düğümü.  
  
 Aşağıdaki çizimde, grafik ve bir küp uygulanan gölgelendirici önizlemesini tamamlanmış gölgelendirici gösterir.  
  
> [!NOTE]
>  Bu çizimde, bir düzlemi Önizleme şekil olarak kullanılır ve bir doku daha iyi gölgelendirici etkisini göstermek için belirtilen.  
  
 ![Gölgelendirici grafik ve etkisini önizlemesini](../designers/media/digit-grayscale-effect.png "basamaklı gri tonlamalı etkisi")  
  
 Belirli şekillerin daha iyi önizlemeleri için bazı gölgelendiriciler sağlayabilir. Gölgelendirici Tasarımcısı'nda gölgelendiriciler önizleme hakkında daha fazla bilgi için bkz: [gölgelendirici Tasarımcısı](../designers/shader-designer.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir 3B modele gölgelendirici uygulama](../designers/how-to-apply-a-shader-to-a-3-d-model.md)   
 [Nasıl yapılır: bir gölgelendirici dışarı aktarma](../designers/how-to-export-a-shader.md)   
 [Görüntü Düzenleyicisi](../designers/image-editor.md)   
 [Gölgelendirici Tasarımcısı](../designers/shader-designer.md)   
 [Gölgelendirici Tasarımcısı Düğümleri](../designers/shader-designer-nodes.md)