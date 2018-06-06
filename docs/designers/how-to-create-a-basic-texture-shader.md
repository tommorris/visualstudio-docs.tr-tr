---
title: 'Nasıl Yapılır: Temel Doku Gölgelendiricisi Oluşturma'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 5af113fb-6415-4be0-8b23-10fddb10e80a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c73ba8007bf107f9dae5cc1422fb582aa5415916
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747059"
---
# <a name="how-to-create-a-basic-texture-shader"></a>Nasıl Yapılır: Temel Doku Gölgelendiricisi Oluşturma

Bu makalede gölgelendirici Tasarımcısı ve yönlendirilmiş grafik gölgelendirici dili (DGSL) tek doku gölgelendirici oluşturmak için nasıl kullanılacağı gösterilmektedir. Bu gölgelendirici son renk doğrudan RGB ve doku örneklenen alfa değerleri ayarlar.

## <a name="create-a-basic-texture-shader"></a>Temel doku gölgelendiricisi oluşturma

Temel, tek doku gölgelendirici doğrudan son çıkış rengi renk ve alfa değerleri bir doku örnek yazarak uygulayabilirsiniz.

Başlamadan önce emin olun **özellikleri** penceresi ve **araç** görüntülenir.

1.  Çalışmak için DGSL gölgelendirici oluşturun. Başlarken bölümünde DGSL gölgelendirici projenize ekleme hakkında daha fazla bilgi için bkz: [gölgelendirici Tasarımcısı](../designers/shader-designer.md).

2.  Silme **nokta rengi** düğümü. İçinde **seçin** modunu Seç **nokta rengi** düğümü ve ardından menü çubuğunda, **Düzenle**, **silmek**. Bu, sonraki adımda eklenen düğüm için yer sağlar.

3.  Ekleme bir **doku örnek** grafiğe düğüm. İçinde **araç**altında **doku**seçin **doku örnek** ve tasarım yüzeyine taşıyın.

4.  Ekleme bir **doku koordine** grafiğe düğüm. İçinde **araç**altında **doku**seçin **doku koordine** ve tasarım yüzeyine taşıyın.

5.  Uygulanacak bir doku seçin. İçinde **seçin** modunu seçin **doku örnek** düğümünü ve ardından **özellikleri** penceresinde kullanarak kullanmak istediğiniz doku belirtin **Filename**  özelliği.

6.  Doku genel olarak erişilebilir hale getirir. Seçin **doku örnek** düğümünü ve ardından **özellikleri** penceresindeki ayarlayın **erişim** özelliğine **ortak**. Başka bir aracından gibi doku ayarlayabilirsiniz artık **Model Düzenleyicisinde**.

7.  Doku koordinatları doku örneğe bağlanın. İçinde **seçin** modu, taşıma **çıkış** , terminal **doku koordine** düğüme **UV** , terminal **doku Örnek** düğümü. Bu bağlantı belirtilen koordinatlarının adresindeki doku örnekleri.

8.  Doku örnek son renk bağlayın. Taşıma **RGB** , terminal **doku örnek** düğüme **RGB** , terminal **son renk** düğümünü ve ardından taşıyın **Alfa** , terminal **doku örnek** düğüme **alfa** , terminal **son renk** düğümü.

Aşağıdaki çizimde, grafik ve bir küp uygulanan gölgelendirici önizlemesini tamamlanmış gölgelendirici gösterir.

> [!NOTE]
> Bu çizimde, bir düzlemi Önizleme şekil olarak kullanılır ve bir doku daha iyi gölgelendirici etkisini göstermek için belirtilen.

![Gölgelendirici grafik ve etkisini önizlemesi](../designers/media/digit-texture-effect.png)

Belirli şekillerin daha iyi önizlemeleri için bazı gölgelendiriciler sağlayabilir. Gölgelendirici Tasarımcısı'nda gölgelendiriciler önizleme hakkında daha fazla bilgi için bkz: [gölgelendirici Tasarımcısı](../designers/shader-designer.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: bir gölgelendirici 3B bir modeli için geçerlidir](../designers/how-to-apply-a-shader-to-a-3-d-model.md)
- [Görüntü Düzenleyicisi](../designers/image-editor.md)
- [Gölgelendirici Tasarımcısı](../designers/shader-designer.md)
- [Gölgelendirici Tasarımcısı Düğümleri](../designers/shader-designer-nodes.md)