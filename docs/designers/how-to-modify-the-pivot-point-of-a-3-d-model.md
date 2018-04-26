---
title: 'Nasıl yapılır: bir 3B modelin Pivot noktası değiştirme'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: c20b4ec8-29f5-4ca5-bc39-d4548ca6f573
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d5f6cff8e8890b97e7aeddad69c4a1a3e0ff5db8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-modify-the-pivot-point-of-a-3d-model"></a>Nasıl yapılır: bir 3B modelin Pivot noktası değiştirme

Bu makalede Model Düzenleyicisinde değiştirmek için nasıl kullanılacağı gösterilmektedir *pivot noktası* 3D model. Pivot noktası, nesne döndürme ve ölçeklendirme için matematiksel merkezini tanımlar alanda noktasıdır.

## <a name="modify-the-pivot-point-of-a-3d-model"></a>Pivot noktası 3D model değiştirme

Pivot noktası değiştirerek 3D model kökeni tanımlayabilirsiniz.

Olduğundan emin olun **özellikleri** penceresi ve **araç** görüntülenir.

1.  Başlangıç bölümünde açıklanan bir gibi varolan bir 3B modeli [nasıl yapılır: temel bir 3B Model oluşturmak](../designers/how-to-create-a-basic-3-d-model.md).

2.  Pivot modu girin. Üzerinde **Model Düzenleyicisinde modu** araç, seçin **Özet modu** düğmesi Özet modunu etkinleştirin. Geçici bir kutu görünür **Özet modu** Model Düzenleyicisinde şimdi Özet modunda olduğunu belirtmek için düğmesi. Pivot modunda pivot noktası world alanı nesnesinde yapısı yerine nesnesinin çevirisi gibi işlemleri etkiler.

3.  Pivot noktası nesnesinin değiştirin. İçinde **seçin** modu, nesneyi seçin ve ardından **modeli Görüntüleyicisi** araç seçin **çevir** aracı. Pivot noktası temsil eden bir kutusu tasarım yüzeyine görüntülenir. Pivot noktası nesnesinin değiştirmek için kutunun taşıyın.

     Kutunun taşıyarak, tüm üç boyutta pivot noktası taşıyabilirsiniz. Pivot noktası bir eksen boyunca çevirmek için bu eksen için karşılık gelen oku taşıyın. Çeviri tarafından etkilenen eksen göstermek üzere sarı bir renk için okları ve kutusunu değiştirin.

     Pivot noktası kullanarak da belirtebilirsiniz **Özet çeviri** özelliğinde **özellikleri** penceresi.

    > [!TIP]
    > Nesne döndürerek yeni pivot noktası etkisini görüntüleyebilirsiniz. Döndürmek için kullanın **Döndür** aracı veya değiştirme **döndürme** özelliği.

Değiştirilen pivot noktası olan bir model şöyledir:

![Değiştirilen pivot noktası olan bir ev modelinin](../designers/media/digit-modified-model.png "basamaklı değiştiren modeli")

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: temel bir 3B modeli oluşturma](../designers/how-to-create-a-basic-3-d-model.md)
- [Model Düzenleyicisi](../designers/model-editor.md)