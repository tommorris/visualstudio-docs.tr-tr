---
title: "Nasıl yapılır: bir temel renk gölgelendirici oluşturun | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c301328a-079a-49e8-b688-4749c01657c0
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7c0992b8db46155a709f58714dfd427882674d2f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-basic-color-shader"></a>Nasıl Yapılır: Temel Renk Gölgelendiricisi Oluşturma
Bu belgede gölgelendirici Tasarımcısı ve yönlendirilmiş grafik gölgelendirici dili (DGSL) bir düz renk gölgelendirici oluşturmak için nasıl kullanılacağı gösterilmektedir. Bu gölgelendirici sabit bir RGB rengi değer son rengini belirler.  
  
 Bu belgede, bu etkinlikler gösterir:  
  
-   Grafikten düğümleri kaldırma  
  
-   Grafiğe düğüm ekleme  
  
-   Düğüm özelliklerini ayarlama  
  
-   Düğümlerini bağlayan  
  
## <a name="creating-a-flat-color-shader"></a>Düz renk gölgelendirici oluşturma  
 Son çıktı renge bir RGB rengi sabiti renk değerini yazarak bir düz renk gölgelendirici uygulayabilirsiniz.  
  
 Başlamadan önce emin olun **özellikleri** penceresi ve **araç** görüntülenir.  
  
#### <a name="to-create-a-flat-color-shader"></a>Düz renk gölgelendirici oluşturmak için  
  
1.  Çalışmak için DGSL gölgelendirici oluşturun. Başlarken bölümünde DGSL gölgelendirici projenize ekleme hakkında daha fazla bilgi için bkz: [gölgelendirici Tasarımcısı](../designers/shader-designer.md).  
  
2.  Silme **nokta rengi** düğümü. Kullanım **seçin** seçmek için aracı **nokta rengi** düğümü ve ardından menü çubuğunda, **Düzenle**, **silmek**.  
  
3.  Ekleme bir **renk sabit** grafiğe düğüm. İçinde **araç**altında **sabitleri**seçin **renk sabit** ve tasarım yüzeyine taşıyın.  
  
4.  Bir renk belirtmeniz için **renk sabit** düğümü. Kullanım **seçin** seçmek için aracı **renk sabit** düğümü ve ardından **özellikleri** penceresi, **çıkış** özelliği belirtin bir renk değeri. Turuncu için (1.0, 0,5, 0.2, 1.0) bir değer belirtin.  
  
5.  Renk sabiti son renk bağlayın. Bağlantı oluşturmak için taşıma **RGB** , terminal **renk sabit** düğüme **RGB** , terminal **son renk** düğümü ve ardından taşıma **alfa** , terminal **renk sabit** düğüme **alfa** , terminal **son renk** düğümü. Bu bağlantılar, önceki adımda tanımlanan rengi sabitine son rengini ayarlayın.  
  
 Aşağıdaki çizimde, grafik ve bir küp uygulanan gölgelendirici önizlemesini tamamlanmış gölgelendirici gösterir.  
  
> [!NOTE]
>  Çizimde, daha iyi gölgelendirici etkisini göstermek için turuncu bir renk belirtildi.  
  
 ![Gölgelendirici grafik ve sonucu bir 3 &#45; D modeli](../designers/media/digit-flat-color-effect.png "düz renk efekti basamak")  
  
 Belirli şekillerin daha iyi önizlemeleri için bazı gölgelendiriciler sağlayabilir. Gölgelendirici Tasarımcısı'nda gölgelendiriciler önizleme hakkında daha fazla bilgi için bkz: [gölgelendirici Tasarımcısı](../designers/shader-designer.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir 3B modele gölgelendirici uygulama](../designers/how-to-apply-a-shader-to-a-3-d-model.md)   
 [Nasıl yapılır: bir gölgelendirici dışarı aktarma](../designers/how-to-export-a-shader.md)   
 [Gölgelendirici Tasarımcısı](../designers/shader-designer.md)   
 [Gölgelendirici Tasarımcısı Düğümleri](../designers/shader-designer-nodes.md)