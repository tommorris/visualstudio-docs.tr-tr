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
ms.openlocfilehash: 0a2d25029455f3e263013c4d6063ee7453a283b6
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747111"
---
# <a name="how-to-modify-the-pivot-point-of-a-3d-model"></a>Nasıl yapılır: bir 3B modelin Pivot noktası değiştirme

Bu makalede Model Düzenleyicisinde değiştirmek için nasıl kullanılacağı gösterilmektedir *pivot noktası* 3D model. Pivot noktası, nesne döndürme ve ölçeklendirme için matematiksel merkezini tanımlar alanda noktasıdır.

## <a name="modify-the-pivot-point-of-a-3d-model"></a>3B modelin pivot noktasını değiştirme

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

![Değiştirilen pivot noktası olan bir ev modeli](../designers/media/digit-modified-model.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: temel bir 3B modeli oluşturma](../designers/how-to-create-a-basic-3-d-model.md)
- [Model Düzenleyicisi](../designers/model-editor.md)