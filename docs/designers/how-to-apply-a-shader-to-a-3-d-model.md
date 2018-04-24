---
title: 'Nasıl yapılır: bir gölgelendirici 3B bir modeli için geçerlidir'
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: a3877bd6-abd8-4a9d-842c-6848b6c2f335
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2c01b8921d851a5410923b84959f12131349535d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-apply-a-shader-to-a-3d-model"></a>Nasıl yapılır: bir gölgelendirici 3B bir modeli için geçerlidir

Bu makalede, Model Düzenleyicisinde yönlendirilmiş grafik gölgelendirici dili (DGSL) gölgelendirici 3B bir modele uygulama için nasıl kullanılacağı gösterilmektedir.

## <a name="apply-a-shader-to-a-3d-model"></a>Bir 3B modele gölgelendirici uygulama

Bir 3B modeline ilginç bir görünüm vermek için bir gölgelendirici efekti uygulayabilirsiniz.

Başlamadan önce emin olun **özellikleri** penceresi görüntülenir.

1. Bir veya daha fazla modelleri içeren bir 3B Sahne ile başlar. Uygun bir 3B Sahne yoksa açıklandığı gibi oluşturmak [nasıl yapılır: temel bir 3B Model oluşturmak](../designers/how-to-create-a-basic-3-d-model.md). Ayrıca, modele uygulayabileceğiniz DGSL gölgelendirici sahip olmanız gerekir. Uygun gölgelendirici yoksa açıklandığı gibi oluşturmak [nasıl yapılır: temel bir renk gölgelendirici oluşturmak](../designers/how-to-create-a-basic-color-shader.md) ve devam etmeden önce bir dosyaya, kaydedilen olduğundan emin olun.

2. İçinde **seçin** modunu seçin, istediğiniz modeli uygulamak gölgelendirici ve ardından **özellikleri** penceresi, **Filename** özelliği **etkisi**  özelliği Grup, modele uygulamak istediğiniz DGSL gölgelendirici belirtin.

Temel renk etkisi uygulanan bir model şöyledir:

![3&#45;temel renk etkisi gösterilmektedir D Sahne](../designers/media/digit-3d-model-effect.png)

Bir model gölgelendirici uyguladıktan sonra gölgelendirici Tasarımcısı'nda model seçerek ve ardından açmadan **özellikleri** penceresi, **(Gelişmiş)** özelliği **etkisi**özellik grubu, üç nokta seçerek (**...** ) düğmesi.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: temel bir 3B modeli oluşturma](../designers/how-to-create-a-basic-3-d-model.md)
- [Nasıl Yapılır: Temel Renk Gölgelendiricisi Oluşturma](../designers/how-to-create-a-basic-color-shader.md)
- [Model Düzenleyicisi](../designers/model-editor.md)
- [Gölgelendirici Tasarımcısı](../designers/shader-designer.md)