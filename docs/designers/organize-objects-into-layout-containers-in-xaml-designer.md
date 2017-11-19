---
title: "XAML Tasarımcısı'nda Düzen kapsayıcılarına nesneleri düzenlemek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29c80c38-0fa3-48d6-b3a8-3b864f482e44
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c5635f5da028283e6683548ec4388f7b3bfcbd8d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="organize-objects-into-layout-containers-in-xaml-designer"></a>XAML Tasarımcısı’nda nesneleri düzen kapsayıcılarına yerleştirme
Bir sayfada görünecek nesneleri oluşturulacağı yeri düşünün; görüntüleri, düğmeler ve videolar gibi nesneleri. Satır ve sütunları tek bir satıra dikey veya yatay veya sabit konumlarda görünmesini istediğiniz olabilir.  
  
 Sayfa nasıl görünebilir hakkında düşünmek ettikten sonra bir düzen paneli seçin. Nesnelerinizi eklemek için bir şey gerektiğinden tüm sayfaları ile başlatın. Varsayılan olarak, bu bir **kılavuz** ancak bunu değiştirebilirsiniz.  
  
 Düzen panelleri sayfasında nesneleri Düzenle yardımcı olur, ancak, birden fazla yaparlar. Bunlar farklı ekran boyutlarına ve çözümlemeleri için tasarım Yardım. Kullanıcıların uygulamanızı çalıştırdığınızda, bir düzen panelinde her şeyi kendi cihazının ekran Gayrimenkul eşleşecek şekilde yeniden boyutlandırır. Doğal olarak, bunu yapmak için düzeninizi istemiyorsanız, düzeni veya tüm düzeni parçası için bu davranışı geçersiz kılabilirsiniz. Yükseklik ve genişlik özelliklerini kontrol eden için kullanabilirsiniz.  
  
 Bu sayfa düzeni paneller ve denetimleri açıklar ve yardımcı kısa videolar için bunları kullanmaya başlama yönlendirir.  
  
> [!NOTE]
>  Bazı videolar karışım veya Expression Blend, Visual Studio ve Visual Studio için Blend olarak aynı XAML Tasarımcısı'nı kullanan başvurabilir.  
  
## <a name="layout-panels"></a>Düzen bölmeleri  
 Bu düzen panelleri birini seçerek sayfanızı başlatın. Sayfanız birden fazla olabilir. Örneğin, ile başlayabilir bir **kılavuz** Düzen panelinde ve ardından ekleyin bir **StackPanel** bir alanına **kılavuz** böylece bu öğenin dikey denetimlerinde düzenleyebilirsiniz.  
  
 Aşağıdaki Düzen panelleri en özellik kullanılır, ancak diğer vardır. Bunları bulabilirsiniz tümü **varlıklar** paneli.  
  
-   [Kılavuz](#Grid)  
  
-   [UniformGrid](#Uniform)  
  
-   [Tuvale](#Canvas)  
  
-   [StackPanel](#Stack)  
  
-   [WrapPanel](#Wrap)  
  
-   [DockPanel](#Dock)  
  
###  <a name="Grid"></a>Kılavuz  
 Nesneleri satırlar ve sütunlar halinde düzenleyin.  
  
 ![](../designers/media/98b234b2-ac3b-441f-9136-98375fee87b7.png "98b234b2-ac3b-441f-9136-98375fee87b7")  
  
 **Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [kullanarak kılavuzları](http://www.popscreen.com/v/6A4hj/Microsoft-Expression-Blend-Using-Grids)  
  
###  <a name="Uniform"></a>UniformGrid  
 Nesneleri eşit ya da Tekdüzen, kılavuz bölgelere düzenleyin. Bu pano, görüntüleri listesini düzenleme için mükemmeldir.  
  
 ![](../designers/media/928b9284-a7e8-4678-875a-656b80b78076.png "928b9284-a7e8-4678-875a-656b80b78076")  
  
 (Yalnızca WPF projeleri için kullanılabilir)  
  
 **Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [UniformGrid ile çalışma](http://www.popscreen.com/v/6A4iq/Microsoft-Expression-Blend-Working-with-a-UniformGrid)  
  
###  <a name="Canvas"></a>Tuvale  
 Nesneleri istediğiniz herhangi bir şekilde düzenleyin. Kullanıcıların uygulamanızı çalıştırdığınızda, bu öğeler ekranında konumlar sabit.  
  
 ![](../designers/media/e1ae27f0-3a57-454e-b580-877dcea8836d.png "e1ae27f0-3a57-454e-b580-877dcea8836d")  
  
 **Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [tuvali ile çalışma](http://www.popscreen.com/v/6A4hT/Microsoft-Expression-Blend-Working-with-the-Canvas)  
  
###  <a name="Stack"></a>StackPanel  
 Tek bir satıra nesneleri yatay veya dikey olarak düzenleyin.  
  
 ![](../designers/media/a85a7b57-b0a8-495e-b985-f0291e41d093.png "a85a7b57-b0a8-495e-b985-f0291e41d093")  
  
 **Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [StackPanel ve WrapPanel ile çalışma](http://www.popscreen.com/v/6A4i5/Microsoft-Expression-Blend-Using-the-StackPanel-and-WrapPanel)  
  
###  <a name="Wrap"></a>WrapPanel  
 Nesneleri sırayla soldan sağa düzenleyin. Bölmenin sağ uçta sınırında dışında yer çalıştığında, *sarmalar* içerikten sonraki satıra vb. soldan sağa üst-alt. Nesneleri üst alta, akması de bir kaydırma panel yönünü dikey soldan sağa yapabilirsiniz.  
  
 (Yalnızca WPF projeleri için kullanılabilir)  
  
 ![](../designers/media/b1c415fb-9a32-4a18-aa0b-308fca994ac9.png "b1c415fb-9a32-4a18-aa0b-308fca994ac9")  
  
 **Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [StackPanel ve WrapPanel ile çalışma](http://www.popscreen.com/v/6A4i5/Microsoft-Expression-Blend-Using-the-StackPanel-and-WrapPanel)  
  
###  <a name="Dock"></a>DockPanel  
 Kalırlar şekilde nesneleri düzenleyin veya *yerleştirme*, bölmenin bir kenara.  
  
 (Yalnızca WPF projeleri için kullanılabilir)  
  
 ![](../designers/media/72d46b58-9a49-4dd5-8af7-6843c0440226.png "72d46b58-9a49-4dd5-8af7-6843c0440226")  
  
 **Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [WPF - DockPanel](https://www.youtube.com/watch?v=EBH_OIM-zPo)  
  
## <a name="layout-controls"></a>Düzen denetimleri  
 Nesnelerinizi de düzen denetimleri ekleyebilirsiniz. Bunlar olarak olmayan özellik bakımından zengin bir düzen paneli, ancak bunları belirli senaryolar için yararlı bulabileceğiniz gibi.  
  
 Aşağıdaki düzen denetimleri en özellik kullanılır ancak başkalarının vardır. Bunları bulabilirsiniz tümü **varlıklar** paneli.  
  
-   [Kenarlık](#Border)  
  
-   [Açılan](#Popup)  
  
-   [ScrollViewer](#Scroll)  
  
-   [UniformGrid](#Uniform)  
  
-   [Viewbox](#View)  
  
###  <a name="Border"></a>Kenarlık  
 Bir sınır, arka plan ya da ikisini geçici bir nesne oluşturun. Yalnızca bir nesneye ekleyebilirsiniz bir **kenarlık**. Kenarlık veya arka plan için birden fazla nesne uygulamak istiyorsanız, Düzen paneline ekleme **kenarlık**. Ardından, nesneleri bu panel veya denetim ekleyin.  
  
 ![](../designers/media/e761238b-99fd-43c5-bbc4-57538b8289ff.png "e761238b-99fd-43c5-bbc4-57538b8289ff")  
  
 **Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [Kenarlıklar ile çalışma](http://www.popscreen.com/v/6A4hB/Microsoft-Expression-Blend-Working-with-Borders)  
  
###  <a name="Popup"></a>Açılan  
 Bir pencerede kullanıcılara bilgileri veya seçenekleri göster. Yalnızca bir nesneye ekleyebilirsiniz bir **açılan**. Varsayılan olarak, bir **açılan** içeren bir **kılavuz** ancak bunu değiştirebilirsiniz.  
  
###  <a name="Scroll"></a>ScrollViewer  
 Bir sayfa veya bir sayfa alanı aşağı etkinleştir kullanır. Yalnızca bir nesneye ekleyebilirsiniz bir **ScrollViewer** bir düzen paneli aşağıdaki gibi eklemek için algılama çok kolaylaştırır şekilde bir **kılavuz** veya **StackPanel**.  
  
 ![](../designers/media/06b326d4-f23d-41a6-b26b-e1aff37572a7.png "06b326d4-f23d-41a6-b26b-e1aff37572a7")  
  
###  <a name="View"></a>Viewbox  
 Yakınlaştırma Denetimi ile ölçek nesneleri çok benzer olacaktır. Yalnızca bir nesneye ekleyebilirsiniz bir **Viewbox**. Birden fazla nesne Bu etkiyi uygulamak istiyorsanız, bir düzen paneline eklemek **ViewBox**ve ardından bu düzeni paneline denetimlerinizi ekleyin.  
  
 (Yalnızca WPF projeleri için kullanılabilir)  
  
 ![](../designers/media/f5b13c66-d918-4141-8a16-bd8f8628687a.png "f5b13c66-d918-4141-8a16-bd8f8628687a")  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XAML Tasarımcısı'nda öğeleri ile çalışma](../designers/working-with-elements-in-xaml-designer.md)   
 [XAML Tasarımcısı kullanarak bir kullanıcı Arabirimi oluşturma](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)