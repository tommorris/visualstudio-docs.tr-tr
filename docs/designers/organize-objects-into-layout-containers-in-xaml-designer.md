---
title: XAML Tasarımcısı’nda nesneleri düzen kapsayıcılarına yerleştirme
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 29c80c38-0fa3-48d6-b3a8-3b864f482e44
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 2da34d180a59212b171e484129df27d94f580a1a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="organize-objects-into-layout-containers-in-xaml-designer"></a>XAML Tasarımcısı’nda nesneleri düzen kapsayıcılarına yerleştirme

Bu makalede, XAML Tasarımcısı için Düzen panelleri ve denetimleri açıklar.

Bir sayfada görünecek nesneleri oluşturulacağı yeri düşünün; görüntüleri, düğmeler ve videolar gibi nesneleri. Satır ve sütunları tek bir satıra dikey veya yatay veya sabit konumlarda görünmesini istediğiniz olabilir.

Sayfa nasıl görünebilir hakkında düşünmek ettikten sonra bir düzen paneli seçin. Nesnelerinizi eklemek için bir şey gerektiğinden tüm sayfaları ile başlatın. Varsayılan olarak bu bir **kılavuz**, ancak bunu değiştirebilirsiniz.

Düzen panelleri sayfasında nesneleri Düzenle yardımcı olur, ancak, birden fazla yaparlar. Bunlar farklı ekran boyutlarına ve çözümlemeleri için tasarım Yardım. Kullanıcıların uygulamanızı çalıştırdığınızda, bir düzen panelinde her şeyi kendi cihazının ekran Gayrimenkul eşleşecek şekilde yeniden boyutlandırır. Doğal olarak, bunu yapmak için düzeninizi istemiyorsanız, düzeni veya tüm düzeni parçası için bu davranışı geçersiz kılabilirsiniz. Yükseklik ve genişlik özelliklerini kontrol eden için kullanabilirsiniz.

## <a name="layout-panels"></a>Düzen bölmeleri

Bu düzen panelleri birini seçerek sayfanızı başlatın. Sayfanız birden fazla olabilir. Örneğin, ile başlayabilir bir **kılavuz** Düzen panelinde ve ardından ekleyin bir **StackPanel** bir alanına **kılavuz** böylece bu öğenin dikey denetimlerinde düzenleyebilirsiniz.

Aşağıdaki Düzen panelleri en özellik kullanılır, ancak diğer vardır. Bunları bulabilirsiniz tümü **varlıklar** paneli.

- [Kılavuz](#Grid)

- [UniformGrid](#UniformGrid)

- [Tuval](#Canvas)

- [StackPanel](#stackpanel)

- [WrapPanel](#wrappanel)

- [DockPanel](#dockpanel)

### <a name="grid"></a>Kılavuz

Nesneleri satırlar ve sütunlar halinde düzenleyin.

![Kılavuz düzeni paneli](../designers/media/98b234b2-ac3b-441f-9136-98375fee87b7.png)

### <a name="uniformgrid"></a>UniformGrid

Nesneleri eşit ya da Tekdüzen, kılavuz bölgelere düzenleyin. Bu pano, görüntüleri listesini düzenleme için mükemmeldir.

![UniformGrid düzeni paneli](../designers/media/928b9284-a7e8-4678-875a-656b80b78076.png)

(Yalnızca WPF projeleri için kullanılabilir.)

### <a name="canvas"></a>Tuval

Nesneleri istediğiniz herhangi bir şekilde düzenleyin. Kullanıcıların uygulamanızı çalıştırdığınızda, bu öğeler ekranında konumlar sabit.

![Tuvale düzeni paneli](../designers/media/e1ae27f0-3a57-454e-b580-877dcea8836d.png)

### <a name="stackpanel"></a>StackPanel

Tek bir satıra nesneleri yatay veya dikey olarak düzenleyin.

![StackPanel düzeni paneli](../designers/media/a85a7b57-b0a8-495e-b985-f0291e41d093.png)

### <a name="wrappanel"></a>WrapPanel

Nesneleri sırayla soldan sağa düzenleyin. Bölmenin sağ uçta sınırında dışında yer çalıştığında, *sarmalar* içerikten sonraki satıra vb. soldan sağa üst-alt. Nesneleri üst alta, akması de bir kaydırma panel yönünü dikey soldan sağa yapabilirsiniz.

(Yalnızca WPF projeleri için kullanılabilir.)

![WrapPanel düzeni paneli](../designers/media/b1c415fb-9a32-4a18-aa0b-308fca994ac9.png)

### <a name="dockpanel"></a>DockPanel

Kalırlar şekilde nesneleri düzenleyin veya *yerleştirme*, bölmenin bir kenara.

(Yalnızca WPF projeleri için kullanılabilir.)

![DockPanel düzeni paneli](../designers/media/72d46b58-9a49-4dd5-8af7-6843c0440226.png)

**Kısa bir video izlemek:** ![Oynat düğmesini](../designers/media/bldadminconsoleinitialconfigicon.PNG) [WPF - DockPanel](https://www.youtube.com/watch?v=EBH_OIM-zPo)

## <a name="layout-controls"></a>Düzen denetimleri

Nesnelerinizi de düzen denetimleri ekleyebilirsiniz. Bunlar olarak olmayan özellik bakımından zengin bir düzen paneli, ancak bunları belirli senaryolar için yararlı bulabileceğiniz gibi.

Aşağıdaki düzen denetimleri en popüler olduğu, ancak diğer vardır. Bunları bulabilirsiniz tümü **varlıklar** paneli.

- [Kenarlık](#Border)

- [Açılan Pencere](#Popup)

- [ScrollViewer](#scrollviewer)

- [Viewbox](#viewbox)

### <a name="border"></a>Kenarlık

Bir sınır, arka plan ya da ikisini geçici bir nesne oluşturun. Yalnızca bir nesneye ekleyebilirsiniz bir **kenarlık**. Kenarlık veya arka plan için birden fazla nesne uygulamak istiyorsanız, Düzen paneline ekleme **kenarlık**. Ardından, nesneleri bu panel veya denetim ekleyin.

![Kenarlık düzen denetimi](../designers/media/e761238b-99fd-43c5-bbc4-57538b8289ff.png)

### <a name="popup"></a>Açılan Pencere

Bir pencerede kullanıcılara bilgileri veya seçenekleri göster. Yalnızca bir nesneye ekleyebilirsiniz bir **açılan**. Varsayılan olarak, bir **açılan** içeren bir **kılavuz** ancak bunu değiştirebilirsiniz.

### <a name="scrollviewer"></a>ScrollViewer

Bir sayfa veya bir sayfa alanı aşağı etkinleştir kullanır. Yalnızca bir nesneye ekleyebilirsiniz bir **ScrollViewer** bir düzen paneli aşağıdaki gibi eklemek için algılama çok kolaylaştırır şekilde bir **kılavuz** veya **StackPanel**.

![ScrollViewer düzen denetimi](../designers/media/06b326d4-f23d-41a6-b26b-e1aff37572a7.png)

### <a name="viewbox"></a>Viewbox

Yakınlaştırma Denetimi ile ölçek nesneleri çok benzer olacaktır. Yalnızca bir nesneye ekleyebilirsiniz bir **Viewbox**. Birden fazla nesne Bu etkiyi uygulamak istiyorsanız, bir düzen paneline eklemek **ViewBox**ve ardından bu düzeni paneline denetimlerinizi ekleyin.

(Yalnızca WPF projeleri için kullanılabilir.)

![ViewBox düzen denetimi](../designers/media/f5b13c66-d918-4141-8a16-bd8f8628687a.png)

## <a name="see-also"></a>Ayrıca bkz.

- [XAML Tasarımcısı’nda öğelerle çalışma](../designers/working-with-elements-in-xaml-designer.md)
- [XAML Tasarımcısı’nı kullanarak bir kullanıcı arabirimi oluşturma](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)