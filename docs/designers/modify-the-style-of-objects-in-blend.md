---
title: "Blend'de Nesnlerin stilini değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31192d2c-5b84-41bc-94c0-898638c170bd
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0133ced82f35a8daefeb3dcaaacd4822f5cad345
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="modify-the-style-of-objects-in-blend"></a>Blend'de nesnlerin stilini değiştirme
Özelliklerini ayarlamak için bir nesne özelleştirmek için en kolay yolu olan **özellikleri** bölmesi.  
  
 Yeniden kullanma ayarları veya ayar gruplarını istiyorsanız, yeniden kullanılabilir bir kaynak oluşturun. Bunun bir *stili*, *şablonu*, ya da özel bir renk gibi basit bir şey. Bir denetim durumu üzerinde farklı bağlı olarak görüntülenirler de yapabilirsiniz. Örneğin, kullanıcı tıklattığında bir düğme yeşil etkinleştirir.  
  
 **Bu konudaki**:  
  
-   [Fırçalar: bir nesne görünümünü değiştirme](#Brushes)  
  
-   [Stilleri ve şablonları: denetimleri arasında tutarlı bir görünüm oluşturma](#Styles)  
  
-   [Visual durumlar: kendi durumuna bağlı bir denetiminin görünümünü değiştirme](#Visual)  
  
-   [Kaynaklar: renk, stil ve şablonları oluşturmak ve bunları daha sonra yeniden](#Resources)  
  
##  <a name="Brushes"></a>Fırçalar: bir nesne görünümünü değiştirme  
 Görünümünü değiştirmek istiyorsanız fırça nesneye uygulanır.  
  
 **Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [Fırçalar Düzenleyicisi](http://www.popscreen.com/v/6A4mO/Microsoft-Expression-Blend-The-Brushes-Editor).  
  
### <a name="paint-a-repeating-image-or-pattern-on-an-object"></a>Yinelenen bir resim veya desen bir nesne üzerinde boyama  
 Yinelenen bir resim veya desen bir nesne üzerinde kullanarak boyamak bir *döşeme fırça*.  
  
 Döşeme Fırça oluşturma için oluşturarak başlayın bir *görüntü fırça*, *fırça çizim*, veya *visual fırça* kaynak.  
  
 Resim fırçası görüntü kullanarak oluşturun. Aşağıdaki çizimler görüntü fırça, döşeli görüntü fırça ve çevrilmiş görüntü fırça gösterir.  
  
 ![](../designers/media/81f84f56-906d-456b-8288-d77da1e01e31.png "81f84f56-906d-456b-8288-d77da1e01e31") ![](../designers/media/d3782ca8-64da-47a4-a095-c6cdd0fa47a2.png "d3782ca8-64da-47a4-a095-c6cdd0fa47a2") ![](../designers/media/38ae3691-f3f1-4a1e-82ca-c7fa164bf56e.png "38ae3691-f3f1-4a1e-82ca-c7fa164bf56e")  
  
 Çizim Fırçası gibi bir yol veya şekil çizme vektör kullanarak oluşturun. Aşağıdaki çizimler çizim Fırçası, döşeli çizim Fırçası ve çevrilmiş çizim Fırçası gösterir.  
  
 ![](../designers/media/197666ac-ef57-4c5c-9779-669e991a00a5.png "197666ac-ef57-4c5c-9779-669e991a00a5") ![](../designers/media/ba09cda3-4cee-40ba-b3d4-edc032158bdc.png "ba09cda3-4cee-40ba-b3d4-edc032158bdc") ![](../designers/media/15bf6021-620c-4490-9eae-086153d3f14f.png "15bf6021-620c-4490-9eae-086153d3f14f")  
  
 Denetimindeki bir düğme gibi visual Fırça oluşturma. Aşağıdaki çizimler visual fırça ve döşenir visual fırça göstermektedir.  
  
 ![](../designers/media/fb6c90e0-153c-48fe-b563-e601beac6227.png "fb6c90e0-153c-48fe-b563-e601beac6227")![](../designers/media/e261b99f-7d8f-4d91-bc84-19c7beccc255.png "e261b99f-7d8f-4d91-bc84-19c7beccc255")  
  
 **Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [Döşeme fırçaları](http://www.popscreen.com/v/6A4iM/Microsoft-Expression-Blend-Tile-Brushes).  
  
##  <a name="Styles"></a>Stilleri ve şablonları: denetimleri arasında tutarlı bir görünüm oluşturma  
 Bir kez Tasarım görünümünü ve davranışını ve böylece tek tek korumak yok Bu tasarımı diğer denetimleri uygulayın.  
  
 **Stil kullanmalısınız?** : Varsayılan özelliklerini (örneğin, bir düğme rengi) ayarlamak istiyorsanız kullanın bir *stili*. Hatta, stil için uyguladığınız sonra bir denetim değiştirebilirsiniz.  
  
 **Bir şablon kullanmalısınız?** : Bir denetim yapısını değiştirmek istiyorsanız, kullanmak bir *şablon*. Grafik veya logo bir düğmeye dönüştürme düşünün. Bir şablon uyguladığınız sonra bir denetim değiştiremezsiniz.  
  
### <a name="create-a-template-or-style"></a>Bir şablonu veya stil oluşturma  
 Şablon oluşturmanın iki yolu vardır. Bir denetime, yüzeyinde herhangi bir nesne dönüştürebilir veya varolan bir denetimi şablonunuzu temel alabilir.  
  
 Herhangi bir nesne için bir denetim şablonu dönüştürmek için nesneyi seçin ve ardından **Araçları** menüsünde seçin **olun içine denetim**.  
  
 Şablonunuzu var olan bir denetim temel almasını istiyorsanız, bir nesne seçin. Ardından, çalışma yüzeyi üst kısmında, içerik haritası düğmesini seçin, seçin **Şablonu Düzenle**ve ardından **bir kopyasını düzenlemek** veya **oluşturma boş**.  
  
 ![](../designers/media/5ebdb33f-aad2-4c10-a328-5e8b04c56a36.png "5ebdb33f-aad2-4c10-a328-5e8b04c56a36")  
  
 Bir stil oluşturmak için nesneyi seçin ve ardından **nesne** menüsünde seçin **stili Düzenle**ve ardından **bir kopyasını düzenlemek** veya **boş oluştur**.  
  
-   Seçin **bir kopyasını düzenlemek** varsayılan stil veya şablon denetimi ile başlatmak için.  
  
-   Seçin **boş oluştur** baştan başlamak için.  
  
 **Düzenle geçerli** seçeneği, yalnızca bir stil veya önceden oluşturduğunuz şablonu düzenlerseniz görünür. Bir denetim için varsayılan Sistem şablonu kullanmaya devam görünmeyecektir.  
  
 İçinde **stil kaynağı oluştur** iletişim kutusu, ya da adını stil veya şablon daha sonra kullanmak ya da bu türdeki tüm denetimler için stil veya şablon uygulayabilirsiniz.  
  
 ![](../designers/media/4818ee6a-ce60-4b79-91c8-3b1871829eea.png "4818ee6a-ce60-4b79-91c8-3b1871829eea")  
  
> [!NOTE]
>  Stilleri veya her tür denetimi için şablonlar oluşturulamıyor. Bir denetim bunları desteklemiyorsa, içerik haritası düğmesi çalışma yüzeyi gösterilmez.  
>   
>  Ana belgenizi düzenleme kapsamına dönmek için tıklatın **dönmek için kapsam** ![](../designers/media/55844eb3-ed98-4f20-aa66-a6f5b23eeb2b.png "55844eb3-ed98-4f20-aa66-a6f5b23eeb2b").  
>   
>  ![](../designers/media/4a5612e1-7a28-4587-b870-0fe7112ec2ad.png "4a5612e1-7a28-4587-b870-0fe7112ec2ad")  
  
 **Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [stil oluşturma](http://www.microsoft.com/showcase/details.aspx?uuid=9b8e86e2-8e90-4d61-81af-fa5b5afb3e95).  
  
 **Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [Expression Blend bir denetim şablonu oluşturma](http://msdn.microsoft.com/expression/cc263912.aspx).  
  
### <a name="apply-a-style-or-template-to-a-control"></a>Stil veya şablon için bir denetim Uygula  
 Bir nesneye sağ [nesneleri ve zaman çizelgesi](http://msdn.microsoft.com/en-us/135a5a5e-ec6d-4f38-8827-60e284cd5f57) paneli, seçin **Şablonu Düzenle**ve ardından **geçerli kaynak**.  
  
 ![](../designers/media/dc12debc-7711-47d9-84ce-10322a384397.png "dc12debc-7711-47d9-84ce-10322a384397")  
  
### <a name="restore-the-default-style-or-template-of-a-control"></a>Varsayılan stil veya şablon bir denetimin geri yükleme  
 Denetimi seçin ve [özellikleri](http://msdn.microsoft.com/en-us/135a5a5e-ec6d-4f38-8827-60e284cd5f57) paneli, bulun **stili** veya **şablonu** özelliği. Ardından **Gelişmiş Seçenekler** ![](../designers/media/12e06962-5d8a-480d-a837-e06b84c545bb.png "12e06962-5d8a-480d-a837-e06b84c545bb")ve ardından **sıfırlama** kısayol menüsünde.  
  
##  <a name="Visual"></a>Visual durumlar: kendi durumuna bağlı bir denetiminin görünümünü değiştirme  
 Denetimlerin Kullanıcı etkileşimlerine dayalı farklı görsel görünümler olabilir. Örneğin, bir kullanıcı bağlantıya tıkladığında veya animasyonun çalıştırabilir yeşile bir düğme yapabilirsiniz. Kısaltın veya geçişleri kullanarak görsel durumlarını arasındaki süreyi uzatın.  
  
 ![](../designers/media/a95c671a-5639-40b9-83db-1e6b214330d5.png "a95c671a-5639-40b9-83db-1e6b214330d5")  
  
 **Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [WPF denetimleri durumunu yöneten](https://www.youtube.com/watch?v=m0PlkF5i6uw).  
  
##  <a name="Resources"></a>Kaynaklar: renk, stil ve şablonları oluşturmak ve bunları daha sonra yeniden  
 Bir kaynağa projenizdeki herhangi bir şeyi dönüştürebilirsiniz. Farklı yerlerde uygulamanızda yeniden bir nesne bir kaynaktır. Örneğin, bir kez bir renk oluşturmak, bir kaynak olun ve sonra o renk birkaç nesneler üzerinde kullanın. Tüm bu nesneleri rengini değiştirmek için yalnızca renk kaynağı değiştirin.  
  
 ![](../designers/media/89203705-cf66-46e0-b153-52a23cd744f7.png "89203705-cf66-46e0-b153-52a23cd744f7")![](../designers/media/6bff8b19-3cd5-41a0-bbf9-ff65532d5aae.png "6bff8b19-3cd5-41a0-bbf9-ff65532d5aae")  
  
 **Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [kısa bir touch kaynaklardaki](http://www.popscreen.com/v/6A4k7/Microsoft-Expression-Blend-Brief-Touch-on-Resources).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio için Blend'i kullanarak kullanıcı Arabirimi oluşturma](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)