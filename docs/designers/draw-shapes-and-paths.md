---
title: "Şekiller ve yollar çizin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5378c59-e2e5-49f0-91f1-aa82d984a33c
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c51f7217942f755eee45c4901cf0f8eecdbac605
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="draw-shapes-and-paths"></a>Şekiller ve yollar çizin
XAML Tasarımcısı'nda bir *şekli* tam ne beklediğiniz olduğundan. Örneğin: dikdörtgen, daire veya elips. A *yolu* bir şekil, daha esnek bir sürümüdür. Bunları yeniden şekillendirmek gibi şeyler veya bunları birlikte form yeni şekillere birleştirebilirsiniz.  
  
 Şekiller ve yollar da yüksek çözünürlüklü ekranlar ölçeklendirmek için vektör grafikleri kullanın. Vektör grafikleri hakkında daha fazla bilgi edinmek istiyorsanız, bkz: [vektör grafikleri nelerdir](https://www.youtube.com/watch?v=MoCSwF0n-io) veya [vektör grafikleri](http://www.webopedia.com/TERM/V/vector_graphics.html).  
  
 **Bu konuda:**  
  
-   [Bir şekil çizme](#Shape)  
  
-   [Yol çizme](#Path)  
  
-   [Bir şekli bir yola Dönüştür](#Convert)  
  
-   [Yolları Birleştir](#Combine)  
  
-   [Bileşik yol oluşturma](#Compound)  
  
-   [Kırpma yolu oluşturun](#Clipping)  
  
##  <a name="Shape"></a>Bir şekil çizme  
 Şekilleri bulabilirsiniz **varlıklar** paneli.  
  
 ![Şekil kategorisini varlıklarını Masası](../designers/media/b4_shapes_assetspanel.png "b4_Shapes_AssetsPanel")  
  
 İstediğiniz herhangi bir şekil çalışma yüzeyine sürükleyin. Ardından, ölçeklendirme, döndürme, taşıyabilir veya şekli eğme şekil üzerinde tanıtıcıları kullanabilirsiniz.  
  
 ![](../designers/media/84261e83-3091-4490-ab58-4218b188439e.png "84261e83-3091-4490-ab58-4218b188439e")  
  
##  <a name="Path"></a>Yol çizme  
 Bir yolu, bağlı çizgiler ve eğrilerle dizisidir. Kullanılamayan ilginç şekiller oluşturmak için bir yol kullanın **varlıklar** paneli.  
  
 Çizgi, kalem veya kalem kullanarak bir yol çizebilirsiniz. Bu araçlar bulabilirsiniz **Araçları** paneli.  
  
 ![](../designers/media/717956a8-b6a5-4e37-8af3-70bcfc78c82a.png "717956a8-b6a5-4e37-8af3-70bcfc78c82a") ![ ] (../designers/media/8fbbbb21-be83-4cf6-903b-3a49f00c9860.png "8fbbbb21-be83-4cf6-903b-3a49f00c9860")  
  
### <a name="draw-a-straight-line"></a>Düz çizgi çizme  
 Kullanım **kalem** aracı ![ ] (../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png "894f8612-e0ed-4e00-84cf-a9bc8f38fc54"), veya **satır** aracı ![ ] (../designers/media/eb618397-5283-48be-8396-3449be7b6fbf.png "eb618397-5283-48be-8396-3449be7b6fbf").  
  
 **Kalem aracını kullanarak** ![ ] (../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png "894f8612-e0ed-4e00-84cf-a9bc8f38fc54")  
  
 Çalışma yüzeyi başlangıç noktasını tanımlamak için bir kez tıklatın ve satırın sonuna tanımlamak üzere yeniden tıklayın.  
  
 **Satırı aracını kullanarak** ![ ] (../designers/media/eb618397-5283-48be-8396-3449be7b6fbf.png "eb618397-5283-48be-8396-3449be7b6fbf")  
  
 Yüzeyinde çizgiyi başlatmak istediğiniz sürükleyin ve sona eklenecek satırı istediğiniz noktada bırakın.  
  
### <a name="draw-a-curve"></a>Eğri çizme  
 Kullanım **kalem** aracı ![ ] (../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png "894f8612-e0ed-4e00-84cf-a9bc8f38fc54").  
  
 Bir satırın başlangıç noktasını tanımlayın ve ardından istenen eğri oluşturmak için işaretçinizi sürükleme için yüzeyinde bir kez tıklatın.  
  
 Yolu kapatmak istiyorsanız, ilk satırın noktasında'ı tıklatın.  
  
### <a name="change-the-shape-of-a-curve"></a>Eğrinin şeklini değiştirme  
 Kullanım **doğrudan seçim** aracı ![ ] (../designers/media/6dd6571f-c116-451d-8dd2-1f88b8406362.png "6dd6571f-c116-451d-8dd2-1f88b8406362").  
  
 Şeklin tıklatın ve ardından herhangi bir noktasını eğri şekiller değiştirmek için Şekil üzerinde sürükleyin.  
  
### <a name="draw-a-free-form-path"></a>Serbest form yolu çizme  
 Kullanım **kalem** aracı ![ ] (../designers/media/509dc167-734f-46c9-b012-987ee63450cd.png "509dc167-734f-46c9-b012-987ee63450cd").  
  
 Gerçek bir Kurşun kullanarak yaptığınız gibi yüzeyinde serbest biçimli yolu çizin.  
  
### <a name="remove-part-of-a-path"></a>Yolunun bir bölümü kaldırılamıyor  
 Kullanım **doğrudan seçim** aracı ![ ] (../designers/media/6dd6571f-c116-451d-8dd2-1f88b8406362.png "6dd6571f-c116-451d-8dd2-1f88b8406362").  
  
 Silin ve ardından istediğiniz kesimi içeren yolu seçin **silmek** düğmesi.  
  
### <a name="remove-a-point-in-a-path"></a>Bir yol için bir nokta Kaldır  
 Kullanım **seçimi** aracı ![ ] (../designers/media/2ff91340-477e-4efa-a0f7-af20851e4daa.png "2ff91340-477e-4efa-a0f7-af20851e4daa")ve **kalem** aracı ![ ] (../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png "894f8612-e0ed-4e00-84cf-a9bc8f38fc54").  
  
 Kullanım **seçimi** aracı ![ ] (../designers/media/2ff91340-477e-4efa-a0f7-af20851e4daa.png "2ff91340-477e-4efa-a0f7-af20851e4daa") yolunu seçin. Ardından, **kalem** aracı ![ ] (../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png "894f8612-e0ed-4e00-84cf-a9bc8f38fc54") kaldırmak istediğiniz noktası tıklatın.  
  
### <a name="add-a-point-to-a-path"></a>Bir yol için bir nokta ekleyin  
 Kullanım **seçimi** aracı ![ ] (../designers/media/2ff91340-477e-4efa-a0f7-af20851e4daa.png "2ff91340-477e-4efa-a0f7-af20851e4daa")ve **kalem** aracı ![ ] (../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png "894f8612-e0ed-4e00-84cf-a9bc8f38fc54").  
  
 Kullanım **seçimi** aracı ![ ] (../designers/media/2ff91340-477e-4efa-a0f7-af20851e4daa.png "2ff91340-477e-4efa-a0f7-af20851e4daa") yolunu seçin. Kullanım **kalem** aracı ![ ] (../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png "894f8612-e0ed-4e00-84cf-a9bc8f38fc54") noktası eklemek istediğiniz yolun herhangi bir yeri tıklatın.  
  
##  <a name="Convert"></a>Bir şekli bir yola Dönüştür  
 Bir şekli bir yolu değiştirmek şekilde değiştirmek için bir yol şekli dönüştürün.  
  
 **Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [yollarını ile çalışma: bir şekli bir yola Dönüştür](https://www.youtube.com/watch?v=Io5bC0-nH6Q#t=147).  
  
##  <a name="Combine"></a>Yolları Birleştir  
 Tek bir yol yolları ve şekiller birleştirebilirsiniz.  
  
 ![](../designers/media/2df17a5d-a338-4ef4-96c5-dae51cc1ca8a.png "2df17a5d-A338-4ef4-96c5-dae51cc1ca8a")  
  
|||||  
|-|-|-|-|  
|![](../designers/media/b1_1.png "B1_1")|Birleştirme öncesi iki şekil|![](../designers/media/b1_4.png "B1_4")|Kesiştir|  
|![](../designers/media/b1_2.png "B1_2")|Birleştir|![](../designers/media/b1_5.png "B1_5")|Örtüşmeyi Dışla|  
|![](../designers/media/b1_3.png "B1_3")|Bölme|![](../designers/media/b1_6.png "B1_6")|Çıkarma|  
  
 **Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [yollarını ile çalışma: yolları Birleştir](https://www.youtube.com/watch?v=Io5bC0-nH6Q#t=195).  
  
##  <a name="Compound"></a>Bileşik yol oluşturma  
 Bileşik yol oluşturduğunuzda, yolların herhangi bir kesişen bölümleri sonuçtan çıkartılır ve sonuçlanan yol en alt yolun görsel özelliklerini kabul eder.  
  
 Bileşik bir yol oluşturduktan sonra istediğiniz zaman parçalayın.  
  
 ![](../designers/media/2157a8aa-d9a7-4de4-8de5-b10d28f08a84.png "2157a8aa-d9a7-4de4-8DE5-b10d28f08a84")  
  
 **Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [yollarını ile çalışma: bileşik yol oluşturma](https://www.youtube.com/watch?v=Io5bC0-nH6Q).  
  
##  <a name="Clipping"></a>Kırpma yolu oluşturun  
 Bir kırpma yolu, kırpma yolu dışına düşen maskelenmiş nesnenin kısımlarını saklayarak, diğer nesneye uygulanan bir yol veya şekildir.  
  
 ![](../designers/media/22471e98-a841-4f39-a3ef-36090cf5a625.png "22471e98-a841-4f39-a3ef-36090cf5a625")  
  
 **Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [yollarını ile çalışma: kırpma yolu oluşturmak](https://www.youtube.com/watch?v=Io5bC0-nH6Q#t=232).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio için Blend’i kullanarak kullanıcı arabirimi oluşturma](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)