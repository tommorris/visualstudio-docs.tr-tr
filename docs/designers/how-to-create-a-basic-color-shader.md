---
title: 'Nasıl Yapılır: Temel Renk Gölgelendiricisi Oluşturma'
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: c301328a-079a-49e8-b688-4749c01657c0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1f4a30315014c4405b811c3e343aee170bfbd365
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-create-a-basic-color-shader"></a>Nasıl Yapılır: Temel Renk Gölgelendiricisi Oluşturma

Bu makalede gölgelendirici Tasarımcısı ve yönlendirilmiş grafik gölgelendirici dili (DGSL) bir düz renk gölgelendirici oluşturmak için nasıl kullanılacağı gösterilmektedir. Bu gölgelendirici sabit bir RGB rengi değer son rengini belirler.

## <a name="create-a-flat-color-shader"></a>Düz renk gölgelendirici oluşturma

Son çıktı renge bir RGB rengi sabiti renk değerini yazarak bir düz renk gölgelendirici uygulayabilirsiniz.

Başlamadan önce emin olun **özellikleri** penceresi ve **araç** görüntülenir.

1.  Çalışmak için DGSL gölgelendirici oluşturun. Başlarken bölümünde DGSL gölgelendirici projenize ekleme hakkında daha fazla bilgi için bkz: [gölgelendirici Tasarımcısı](../designers/shader-designer.md).

2.  Silme **nokta rengi** düğümü. Kullanım **seçin** seçmek için aracı **nokta rengi** düğümü ve ardından menü çubuğunda, **Düzenle**, **silmek**.

3.  Ekleme bir **renk sabit** grafiğe düğüm. İçinde **araç**altında **sabitleri**seçin **renk sabit** ve tasarım yüzeyine taşıyın.

4.  Bir renk belirtmeniz için **renk sabit** düğümü. Kullanım **seçin** seçmek için aracı **renk sabit** düğümü ve ardından **özellikleri** penceresi, **çıkış** özelliği belirtin bir renk değeri. Turuncu için (1.0, 0,5, 0.2, 1.0) bir değer belirtin.

5.  Renk sabiti son renk bağlayın. Bağlantı oluşturmak için taşıma **RGB** , terminal **renk sabit** düğüme **RGB** , terminal **son renk** düğümü ve ardından taşıma **alfa** , terminal **renk sabit** düğüme **alfa** , terminal **son renk** düğümü. Bu bağlantılar, önceki adımda tanımlanan rengi sabitine son rengini ayarlayın.

Aşağıdaki çizimde, grafik ve bir küp uygulanan gölgelendirici önizlemesini tamamlanmış gölgelendirici gösterir.

> [!NOTE]
> Çizimde, daha iyi gölgelendirici etkisini göstermek için turuncu bir renk belirtildi.

![Gölgelendirici grafik ve sonucu 3&#45;D modeli](../designers/media/digit-flat-color-effect.png "düz renk efekti basamak")

Belirli şekillerin daha iyi önizlemeleri için bazı gölgelendiriciler sağlayabilir. Gölgelendirici Tasarımcısı'nda gölgelendiriciler önizleme hakkında daha fazla bilgi için bkz: [gölgelendirici Tasarımcısı](../designers/shader-designer.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: bir gölgelendirici 3B bir modeli için geçerlidir](../designers/how-to-apply-a-shader-to-a-3-d-model.md)
- [Nasıl Yapılır: Gölgelendiriciyi Dışarı Aktarma](../designers/how-to-export-a-shader.md)
- [Gölgelendirici Tasarımcısı](../designers/shader-designer.md)
- [Gölgelendirici Tasarımcısı Düğümleri](../designers/shader-designer-nodes.md)