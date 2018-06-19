---
title: XAML Tasarımcısı'de denetimler ekleme ve bunların davranışlarını değiştirme
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: a80fff74-bf01-41c9-ab85-ada7a873c3a9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: e2ec53e78bc88e18d9ba8e77aa888ffa855b64ea
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31924161"
---
# <a name="insert-controls-and-modify-their-behavior-in-xaml-designer"></a>XAML Tasarımcısı'de denetimler ekleme ve bunların davranışlarını değiştirme

Denetimler kullanıcıların uygulamanızı ile etkileşim kurmasına olanak sağlar. Bunları gerçekleştirmek için de bilgi toplamak için kullanabileceğiniz bir nesne hale getirmeyi veya bir veri kaynağını sorgulaması gibi eylemler.

## <a name="add-controls-to-the-artboard"></a>İçin çalışma yüzeyi denetimleri ekleme

Denetimlerden sürükleyebilirsiniz **varlıklar** üzerine panel **çalışma yüzeyi**ve bunları değiştirme **özellikleri** penceresi.

![Varlıklar sekme denetimleri blend](../designers/media/blend_assetsflipview_xaml.png)

### <a name="make-a-control-out-of-an-image-shape-or-path"></a>Bir görüntü, Şekil veya yolu dışında bir denetim olun

Herhangi bir nesne bir denetime yapabilirsiniz.

![Harmanlama denetimi içine olun iletişim kutusu](../designers/media/blend_makeintocontrol_xaml.png)

Örneğin, bir sayfanın Center'da televizyon resmini düşünün. Denetimleri televizyon düğmeleri gibi ara küçük resimleri dışında hale getirebilir. Ardından, kullanıcıların kanalı değiştirmek için bu düğmeleri tıklayın.

Düğmeleri şimdi denetimleri olduğundan, bu mümkündür. Denetimler ile Kullanıcı etkileşimlerine yanıt verebilir; Bu durumda kullanıcı bir düğmesine tıkladığında.

Bir denetimi yapmak için bir nesne seçin. Ardından **Araçları** menüsünde tıklatın **olun denetim**.

## <a name="make-controls-do-things"></a>Denetimlerin şeyler yapın

Kullanıcıların etkileşime girdiğinde denetimleri eylemleri gerçekleştirebilirsiniz. Örneğin, bunlar bir animasyon başlatabilir, bir veri kaynağını güncelleştirmek veya bir çalmasına.

Kullanım *Tetikleyicileri*, *davranışları*, ve *olayları* şeyler denetimleri yapma.

### <a name="triggers"></a>Tetikleyiciler

A *tetikleyici* bir özelliğini değiştirir veya bir olay veya başka bir özellik değişikliği yanıt olarak bir görevi gerçekleştirir. Örneğin, kullanıcılar üzerine geldiğinizde düğme rengini değiştirebilirsiniz.

!["Tetikleyiciler" paneli](../designers/media/custom_button_blend_propertytriggerinfo.png)

### <a name="behaviors"></a>Davranışlar

A *davranışı* kod yeniden kullanılabilir bir pakettir. Bunu biraz yapmak birden fazla özelliklerini değiştirin. Sorgu veri hizmeti gibi eylemleri gerçekleştirebilirsiniz. Harmanlama küçük koleksiyonu bunları ile gelir ancak daha ekleyebilirsiniz. Çalışma yüzeyi herhangi bir nesne bir davranış sürükleyin ve sonra özelliklerini ayarlayarak davranışını özelleştirin.

![Özellikleri panelinde FluidMoveBehavior](../designers/media/b4_fluidmovebehaviorproperties_sample.png)

**Bir video izlemek:** ![Yürüt simgesinin](../designers/media/bldadminconsoleinitialconfigicon.PNG) [Blend ipuçları: davranışları Kısım 1 için giriş](http://www.bing.com/videos/search?q=Expression%20blend%20behaviors&qs=n&form=QBVR&pq=expression%20blend%20behavior&sc=4-25&sp=-1&sk=#view=detail&mid=CF0DD797ED84DE740904CF0DD797ED84DE740904).

### <a name="events"></a>Olaylar

Ultimate esneklik için işleme bir *olay*. Bazı kodlar yazmak zorunda kalırsınız.