---
title: 'Nasıl Yapılır: Temel Doku Oluşturma'
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 0222e8bf-d29f-421b-9b1f-123d500fa179
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 45bb45c12e7cbdbec37574f371daf4cd6c207fb1
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-create-a-basic-texture"></a>Nasıl Yapılır: Temel Doku Oluşturma
Bu belge, temel bir doku oluşturmak için görüntü düzenleyicisi kullanın gösterilmiştir.

 Bu belgede, bu etkinlikler gösterir:

-   Doku boyutunu ayarlama

-   Ön plan ve arka plan renklerini ayarlama

-   Alfa kanal (Saydamlık) kullanma

-   Kullanarak **doldurun** ve **elips** araçları

-   Aracı özelliklerini ayarlama

## <a name="creating-a-basic-texture"></a>Temel bir doku oluşturma
 Görüntüleri ve oyun veya uygulama için doku oluşturmak ve değiştirmek için görüntü Düzenleyicisi'ni kullanabilirsiniz.

 Aşağıdaki adımlar "hedef Merkezi" hedef temsil eden bir doku oluşturulacağını gösterir. İşiniz bittiğinde, doku aşağıdaki resimde gibi görünmelidir. Daha iyi dokudaki saydamlık göstermek için görüntü Düzenleyicisi görüntülemek için yeşil, Damalı desen kullanmak için yapılandırıldı.

 ![Yeşil renkte gösterilir saydamlık "Hedef Merkezi" hedefle](../designers/media/digit-bullseye-texture-in-editor.png "basamaklı-hedef merkezi-doku--Düzenleyicisi'nde")

 Başlamadan önce emin olun **özellikleri** penceresi görüntülenir. Kullandığınız **özellikleri** penceresi görüntü boyutunu ayarlamak, aracı özelliklerini değiştirmek ve çalışırken renkleri belirtin.

#### <a name="to-create-a-bullseye-target-texture"></a>"Hedef Merkezi" hedef dokusu oluşturmak için

1.  Çalışmak üzere bir doku oluşturun. Başlarken bölümünde bir doku projenize ekleme hakkında daha fazla bilgi için bkz: [görüntü Düzenleyicisi](../designers/image-editor.md).

2.  Görüntü boyutu 512 x 512 piksel olarak ayarlayın. İçinde **özellikleri** penceresindeki değerlerini ayarlayın **genişliği** ve **yükseklik** özelliklerine `512`.

3.  Görüntü Düzenleyicisi araç çubuğunda seçin **doldurun** aracı. **Özellikleri** penceresi özelliklerini görüntüler **doldurun** görüntü özelliklerini birlikte aracı.

4.  Ön plan rengini tamamen saydam siyah olarak ayarlayın. İçinde **özellikleri** penceresi, **renkleri** özellik grubu, select **ön plan**. Değerlerini ayarlamak **R**, **G**, **B**, ve **A** Renk Seçici yanındaki özellikleri `0`.

5.  Görüntü Düzenleyicisi araç çubuğunda seçin **doldurun** aracı tuşuna basın ve Shift tuşunu basılı tutun ve görüntüde herhangi bir noktasını seçin. SHIFT tuşunu kullanarak görüntüdeki rengi değiştirmek için dolgu rengi alfa değeri neden olur; Aksi takdirde, alfa değeri karışım dolgu rengi renk görüntüdeki birlikte için kullanılır.

    > [!IMPORTANT]
    >  Önceki adımda renk seçim ile birlikte bu adım, temel görüntü için çizim "hedef Merkezi" hedef dokuyu hazırlanır sağlar. Resmin saydam siyah doldurulur zaman — ve hedef kenarlık siyah olduğundan — hiçbir yumuşatma yapıları hedef geçici olacaktır.

6.  Görüntü Düzenleyicisi araç çubuğunda seçin **elips** aracı.

7.  Ön plan rengini tamamıyla opak siyah olarak ayarlayın. Değerlerini ayarlamak **R**, **G**, ve **B** özelliklerine `0` değerini **A** özelliğine `255`.

8.  Arka plan rengini tamamıyla opak beyaza ayarlayın. İçinde **özellikleri** penceresi, **renkleri** özellik grubu, select **arka plan**. Değerlerini ayarlamak **R**, **G**, **B**, ve **A** özelliklerine `255`.

9. Elips kenarlık genişliğini ayarla. İçinde **özellikleri** penceresi, **Görünüm** özellik grubu değerini ayarlamak **genişliği** özelliğine `8`.

10. Yumuşatma etkin olduğundan emin olun. İçinde **özellikleri** penceresi, **Görünüm** özelliği grubunda, olduğundan emin olun **yumuşatma** özelliği ayarlanmış.

11. Kullanarak **elips** aracı, bir daire piksel koordinat çizmek `(3, 3)` piksel koordinat için `(508, 508)`. Daha fazla daire çizmek için kolayca, çizerken Shift tuşunu basılı tutun.

    > [!NOTE]
    >  Geçerli işaretçi konumunun piksel koordinatlarını görüntülenir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] durum çubuğu.

12. Arka plan rengini değiştirin. Ayarlama **R** için `44`, **G** için `165`, **B** için `211`, ve **A** için `255`.

13. Piksel koordinat başka bir daire çizmek `(64, 64)` piksel koordinat için `(448, 448)`.

14. Tamamen opak beyaz arka plan rengini değiştirin. Ayarlama **R**, **G**, **B**, ve **A** için `255`.

15. Piksel koordinat başka bir daire çizmek `(128, 128)` piksel koordinat için `(384, 384)`.

16. Arka plan rengini değiştirin. Ayarlama **R** için `255`, **G** ve **B** için `64`, ve **A** için `255`.

17. Piksel koordinat başka bir daire çizmek `(192, 192)` piksel koordinat için `(320, 320)`.

 "Hedef Merkezi" hedef doku tamamlanır. Saydamlığı olan gösterilen görüntünün son İşte.

 ![Tam "hedef"merkezi hedef doku](../designers/media/gfx_image_demo_bullseye.png "gfx_image_demo_bullseye")

 Bir sonraki adım, bu doku MIP düzeylerini oluşturabilirsiniz. Bilgi için bkz: [nasıl yapılır: oluşturma ve değiştirme MIP düzeyleri](../designers/how-to-create-and-modify-mip-levels.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Görüntü Düzenleyicisi](../designers/image-editor.md)