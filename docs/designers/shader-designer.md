---
title: "Gölgelendirici Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.graphics.designer.effectdesigner
- vs.graphics.shaderdesigner
ms.assetid: 5db09a16-b82c-4ba3-8ec9-630cdc109397
caps.latest.revision: "32"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: fb3a7122f561f2c1beaa5674be2220a565586aa4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="shader-designer"></a>Gölgelendirici Tasarımcısı
Bu belge ile nasıl çalışılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] gölgelendirici Designer'ın oluşturmak, değiştirmek ve olarak bilinen özel görsel efektler verme *gölgelendiriciler*.  
  
 HLSL programlama bilmiyorsanız bile oyun veya uygulama için özel görsel efektler oluşturmak için gölgelendirici Tasarımcısı'nı kullanabilirsiniz. Gölgelendirici gölgelendirici Tasarımcısı'nda oluşturmak için yalnızca onu bir grafik düzenleyin; diğer bir deyişle, tasarım yüzeyine eklemek *düğümleri* , verilerin ve işlemlerin temsil eder ve bunları işlemlerini veri işleminin nasıl tanımlanacağını arasında bağlantı kurmak. Böylece sonuç görselleştirebilirsiniz her işlem düğümü, bu noktaya kadar etkili önizlemesi sağlanır. Veriler gölgelendirici çıktısını gösterir son bir düğümü doğru düğümler üzerinden akar.  
  
## <a name="supported-formats"></a>Desteklenen biçimler  
 Bu gölgelendirici biçimleri gölgelendirici Tasarımcısı'nı destekler:  
  
|Biçim Adı|Dosya Uzantısı|Desteklenen işlemler (Görünüm, düzenleme, dışa aktarma)|  
|-----------------|--------------------|-------------------------------------------------|  
|Yönlendirilmiş Grafik gölgelendirici dili|.dgsl|Görünüm, düzenleme|  
|HLSL gölgelendirici (kaynak kodu)|.hlsl|Dışarı aktarma|  
|HLSL gölgelendirici (bayt)|.CSO|Dışarı aktarma|  
|C++ üstbilgi (HLSL bayt dizesi)|.h|Dışarı aktarma|  
  
## <a name="getting-started"></a>Başlarken  
 Bu bölümde, bir DGSL gölgelendirici eklemeyi açıklar, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje ve başlamanıza yardımcı olmak için temel bilgileri sağlar.  
  
#### <a name="to-add-a-dgsl-shader-to-your-project"></a>DGSL gölgelendirici projenize eklemek için  
  
1.  İçinde **Çözüm Gezgini**, gölgelendirici ekleyin ve ardından istediğiniz proje için kısayol menüsünü açın **Ekle**, **yeni öğe**.  
  
2.  İçinde **Yeni Öğe Ekle** iletişim kutusunda **yüklü**seçin **grafik**ve ardından **Visual gölgelendirici grafik (.dgsl)**.  
  
3.  Belirtin **adı** gölgelendirici dosyasının ve **konumu** istediğiniz oluşturulacak.  
  
4.  Seçin **Ekle** düğmesi.  
  
### <a name="the-default-shader"></a>Varsayılan gölgelendirici  
 İsteğe bağlı olarak bir DGSL gölgelendirici oluşturduğunuz her zaman sadece sahip en az bir gölgelendirici başlar bir **nokta rengi** bağlı düğüm **son renk** düğümü. Bu gölgelendirici tam ve işlevsel olsa da, çok yapmaz. Bu nedenle, bir çalışma gölgelendirici oluşturmanın ilk adımı silmek için görülür **nokta rengi** düğümü veya olan bağlantısını kesmeniz **son renk** yer açmak için diğer düğümlere düğümü.  
  
## <a name="working-with-the-shader-designer"></a>Gölgelendirici tasarımcı ile birlikte çalışma  
 Aşağıdaki bölümlerde gölgelendirici tasarımcının özel gölgelendiriciler ile çalışmak için nasıl kullanılacağı açıklanmaktadır.  
  
### <a name="shader-designer-toolbars"></a>Gölgelendirici Designer araç çubukları  
 Araç çubukları içeren gölgelendirici Tasarımcısı DGSL gölgelendirici grafiklerle çalışma yardımcı komutları.  
  
 Gölgelendirici Tasarımcısı durumunu etkileyen komutları bulunur **gölgelendirici Tasarımcısı mod** araç ana [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] penceresi. Tasarım Araçlar ve komutlar bulunur **gölgelendirici Tasarımcısı** gölgelendirici Tasarımcısı tasarım yüzeyine araç.  
  
 Burada **gölgelendirici Tasarımcısı mod** araç çubuğu:  
  
 ![Gölgelendirici Tasarımcısı kalıcı araç. ] (../designers/media/digit-dsd-modal-toolbar.png "DSD kalıcı araç basamak")  
  
 Bu tablo üzerinde öğeleri açıklar **gölgelendirici Tasarımcısı mod** göründükleri soldan sağa doğru sırayla listelenir araç çubuğu:  
  
|Araç Çubuğu Öğesi|Açıklama|  
|------------------|-----------------|  
|**Seçin**|Düğümler ve grafik kenarları ile etkileşim sağlar. Bu modda, düğümleri seçin ve taşıyabilir veya silin ve kenarları oluşturmak veya bunları bölün.|  
|**Yatay kaydırma**|Bir gölgelendirici grafiği pencere çerçevesi göre hareketini sağlar. Kaydırmak için tasarım yüzeyine noktasında seçin ve taşıyabilirsiniz.<br /><br /> İçinde **seçin** modu tuşuna basın ve etkinleştirmek için Ctrl basılı **Pan** geçici olarak modu.|  
|**Yakınlaştır**|Pencere çerçevesi göre daha az veya gölgelendirici grafik ayrıntı görünümünü sağlar. İçinde **yakınlaştırma** modu, tasarım yüzeyine bir nokta seçin ve ardından sağa taşıyın veya yakınlaştırmak için aşağı veya sol veya en fazla yakınlaştırma yetersiz.<br /><br /> İçinde **seçin** modu tuşuna basın ve yakınlaştırmak veya uzaklaştırmak fare tekerleği kullanarak Ctrl basılı tutun.|  
|**Sığdırmak için Yakınlaştır**|Tam gölgelendirici grafiği pencere çerçevede görüntüler.|  
|**Gerçek zamanlı işleme modu**|Gerçek zamanlı işleme etkinleştirildiğinde, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bile herhangi bir kullanıcı eylemi gerçekleştirildiğinde tasarım yüzeyi yeniden çizer. Bu mod, zamanla değişen gölgelendiriciler ile çalıştığınızda kullanışlıdır.|  
|**İle küre Önizleme**|Etkinleştirildiğinde, bir model kürenin gölgelendirici önizlemek için kullanılır. Bir seferde yalnızca bir önizleme şekli etkinleştirilebilir.|  
|**Küp Önizleme**|Etkinleştirildiğinde, bir küp modelinin gölgelendirici önizlemek için kullanılır. Bir seferde yalnızca bir önizleme şekli etkinleştirilebilir.|  
|**Silindir ile Önizleme**|Etkinleştirildiğinde, silindir modelinin gölgelendirici önizlemek için kullanılır. Bir seferde yalnızca bir önizleme şekli etkinleştirilebilir.|  
|**İle koni Önizleme**|Etkinleştirildiğinde, bir model koninin gölgelendirici önizlemek için kullanılır. Bir seferde yalnızca bir önizleme şekli etkinleştirilebilir.|  
|**İle teapot Önizleme**|Etkinleştirildiğinde, bir teapot modelinin gölgelendirici önizlemek için kullanılır. Bir seferde yalnızca bir önizleme şekli etkinleştirilebilir.|  
|**İle düzlemi Önizleme**|Etkinleştirildiğinde, bir düzlemi modelinin gölgelendirici önizlemek için kullanılır. Bir seferde yalnızca bir önizleme şekli etkinleştirilebilir.|  
|**Araç kutusu**|Alternatif olarak gösterir veya gizler **araç**.|  
|**Veri Erişimi**|Alternatif olarak gösterir veya gizler **özellikleri** penceresi.|  
|**Gelişmiş**|Gelişmiş komutları ve seçenekleri içerir.<br /><br /> **Dışarı aktarma**: çeşitli biçimlerde gölgelendirici verilmesini sağlar.<br /><br /> **Dışarı aktarma olarak**: Gölgelendirici ya da HLSL kaynak kodu veya derlenmiş gölgelendirici bayt olarak dışa aktarır. Gölgelendiriciler dışarı aktarma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir gölgelendirici verme](../designers/how-to-export-a-shader.md).<br /><br /> **Grafik motorları**: tasarım yüzeyine görüntülemek için kullanılan Oluşturucu seçimi sağlar.<br /><br /> **İle D3D11 işleme**: Direct3D 11 gölgelendirici Tasarımcısı tasarım yüzeyi işlemek için kullanır.<br /><br /> **İle D3D11WARP işleme**: kullanan Direct3D 11 Windows Gelişmiş Tarama Platform (gölgelendirici Tasarımcısı tasarım yüzeyi işlemek için TÜNELİ).<br /><br /> **Görünüm**: seçimi gölgelendirici Tasarımcısı hakkında ek bilgi sağlar.<br /><br /> **Kare hızı**: etkin olduğunda, geçerli kare hızı tasarım yüzeyine sağ üst köşesinde görüntülenir. Kare hızı, saniye başına çizilen çerçeve sayısıdır.  Bu seçenek, etkinleştirdiğinizde yararlıdır **gerçek zamanlı işleme modunu** seçeneği.|  
  
> [!TIP]
>  Seçebileceğiniz **Gelişmiş** düğmesi son komutu yeniden çalıştırın.  
  
### <a name="working-with-nodes-and-connections"></a>Düğümleri ve bağlantıları ile çalışma  
 Kullanım **seçin** modu eklemek, kaldırmak, yeniden konumlandırmak, bağlanmak ve düğümlerini yapılandırmak için. Bu temel işlemleri gerçekleştirmek nasıl şöyledir:  
  
##### <a name="to-perform-basic-operations-in-select-mode"></a>Seçim modunda temel işlemleri gerçekleştirmek için  
  
-   İşte nasıl:  
  
    -   Grafiğe düğüm eklemek için seçin **araç** ve sonra Tasarım yüzeyine taşıyın.  
  
    -   Grafikten bir düğümü kaldırmak için onu seçin ve Delete tuşlarına basın.  
  
    -   Bir düğümü yeniden konumlandırmak için onu seçin ve ardından yeni bir konuma taşıyın.  
  
    -   İki düğüm bağlanmak için diğer düğümü için bir giriş terminal bir düğümün bir çıktı terminal taşıyın. Uyumlu türleri olan Terminal bağlanabilir. Bir satır Terminal arasında bağlantı gösterir.  
  
    -   Bağlı Terminal birini için kısayol menüsünde bir bağlantıyı kaldırmak isterseniz **bölün bağlantılar**.  
  
    -   Bir düğüm özelliklerini yapılandırmak için düğümü seçin ve ardından **özellikleri** penceresinde özellikler için yeni değerleri belirtin.  
  
### <a name="previewing-shaders"></a>Gölgelendiriciler Önizleme  
 Gölgelendirici uygulamanızı nasıl görüneceğini anlamanıza yardımcı olması için efekti nasıl önizlemesi yapılandırabilirsiniz. Uygulamanızı yaklaşık için işlemek, doku ve diğer malzeme parametreleri yapılandırmak, animasyon zamana dayalı etkileri etkinleştirin ve farklı açılardan Önizleme incelemek için birkaç şekiller birini seçebilirsiniz.  
  
#### <a name="shapes"></a>Şekiller  
 Altı şekiller gölgelendirici Tasarımcısı'nı içerir — bir küre, küp, silindir, koni, bir teapot ve bir düzlemi —, gölgelendirici önizlemek için kullanabilirsiniz. Gölgelendirici bağlı olarak belirli şekillerin daha iyi önizleme verebilir.  
  
###### <a name="to-choose-a-preview-shape"></a>Bir önizleme şekli seçmek için  
  
-   Üzerinde **gölgelendirici Tasarımcısı modları** araç, istediğiniz şekli seçin.  
  
####  <a name="WWS_MaterialParameters"></a>Dokular ve malzeme parametreleri  
 Birçok gölgelendirici dokular ve uygulamanızı nesnesinde her tür için benzersiz bir görünüm oluşturmak için malzeme özelliklerine güvenir. Gölgelendirici uygulamanızı nasıl görüneceğini görmek için doku ve dokular ve uygulamanızda kullanabilirsiniz parametreleri eşleştirmek için Önizleme'yi işlemek için kullanılan malzeme özellikleri ayarlayabilirsiniz.  
  
###### <a name="to-bind-a-different-texture-to-a-texture-register-or-to-modify-other-material-parameters"></a>Bir doku kasaya farklı bir doku bağlamak veya diğer malzeme parametreleri değiştirmek için  
  
1.  İçinde **seçin** modu, tasarım yüzeyine boş alanı seçin. Bu neden **özellikleri** penceresi genel gölgelendirici özelliklerini görüntüleyin.  
  
2.  İçinde **özellikleri** penceresinde değiştirmek istediğiniz doku ve parametre özellikleri için yeni değerleri belirtin.  
  
 Değiştirebileceğiniz gölgelendirici Parametreler şunlardır:  
  
|Parametre|Özellikler|  
|---------------|----------------|  
|**Doku 1** - **doku 8**|**Erişim**: **ortak** modeli Düzenleyicisi'nden ayarlayın; tersi durumda, özellik izin vermek için **özel**.<br /><br /> **Dosya adı**: Bu doku kaydı ile ilişkilendirilmiş doku dosyasının tam yolu.|  
|**Malzeme ortam**|**Erişim**: **ortak** modeli Düzenleyicisi'nden ayarlayın; tersi durumda, özellik izin vermek için **özel**.<br /><br /> **Değer**: dolaylı - veya ortam - aydınlatma nedeniyle geçerli piksel dağıtma rengi.|  
|**Malzeme dağıtma**|**Erişim**: **ortak** modeli Düzenleyicisi'nden ayarlayın; tersi durumda, özellik izin vermek için **özel**.<br /><br /> **Değer**: geçerli piksel doğrudan aydınlatma nasıl diffuses açıklayan bir renk.|  
|**Malzeme Yayıcı**|**Erişim**: **ortak** modeli Düzenleyicisi'nden ayarlayın; tersi durumda, özellik izin vermek için **özel**.<br /><br /> **Değer**: kendi kendine sağlanan aydınlatma nedeniyle geçerli piksel renk katkı.|  
|**Malzeme aynasal**|**Erişim**: **ortak** modeli Düzenleyicisi'nden ayarlayın; tersi durumda, özellik izin vermek için **özel**.<br /><br /> **Değer**: geçerli piksel doğrudan aydınlatma nasıl yansıtır açıklayan bir renk.|  
|**Malzeme aynasal güç**|**Erişim**: **ortak** modeli Düzenleyicisi'nden ayarlayın; tersi durumda, özellik izin vermek için **özel**.<br /><br /> **Değer**: üs. geçerli pikselini aynasal vurgular yoğunluğunu tanımlar.|  
  
#### <a name="time-based-effects"></a>Zamana bağlı etkileri  
 Bazı gölgelendiriciler etkisi canlandırır zamana bağlı bir bileşen var. Etkisi nasıl eylemde göründüğünü göstermek için önizleme birkaç kez saniyede güncelleştirilmesi gerekir. Varsayılan olarak, Önizleme yalnızca gölgelendirici değiştirildiğinde güncelleştirilir; zamana bağlı etkileri görüntüleyebilmesi için bu davranışı değiştirmek için gerçek zamanlı işleme etkinleştirmek zorunda.  
  
###### <a name="to-enable-real-time-rendering"></a>Gerçek zamanlı işleme etkinleştirmek için  
  
-   Gölgelendirici Tasarımcısı araç çubuğundaki seçin **gerçek zamanlı işleme**.  
  
#### <a name="examining-the-effect"></a>Etkisi inceleniyor  
 Birçok gölgelendirici açısı veya tek yönlü ışık görüntüleme gibi değişkenleri etkilenir. Bu değişkenler değiştikçe etkisi nasıl yanıt vereceğini incelemek için Önizleme şekli serbest döndürün ve gölgelendirici nasıl davranacağını uyun.  
  
###### <a name="to-rotate-the-shape"></a>Şekli döndürmek için  
  
-   Tuşuna basın ve Alt, basılı tutun ve ardından tasarım yüzeyine herhangi bir noktasını seçin ve taşıyın.  
  
### <a name="exporting-shaders"></a>Gölgelendiriciler dışarı aktarma  
 Uygulamanızda gölgelendirici kullanmadan önce DirectX özelliğini algılayan bir biçimde dışarı sahip.  
  
 HLSL kaynak kodu veya derlenmiş gölgelendirici bayt olarak gölgelendiriciler dışarı aktarabilirsiniz. HLSL kaynak kodu .hlsl dosya adı uzantısına sahip bir metin dosyasına aktarılır. Gölgelendirici bayt .cso dosya adı uzantısına sahip bir ham ikili dosya veya bir diziye gölgelendirici bayt kodlar C++ üstbilgi (.h) dosyasına aktarılabilir.  
  
 Gölgelendiriciler dışarı aktarma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir gölgelendirici verme](../designers/how-to-export-a-shader.md).  
  
## <a name="keyboard-shortcuts"></a>Klavye kısayolları  
  
|Komut|Klavye kısayolları|  
|-------------|------------------------|  
|Geçiş **seçin** modu|Ctrl+G, Gtrl+Q<br /><br /> S|  
|Geçiş **yakınlaştırma** modu|Ctrl+G, Ctrl+Z<br /><br /> Z|  
|Geçiş **Pan** modu|Ctrl+G, Ctrl+P<br /><br /> K|  
|Tümünü seç|Ctrl+A|  
|Geçerli seçimi sil|Sil|  
|Geçerli seçimi iptal et|Esc|  
|Yakınlaştır|Ctrl+Fare tekerleği ileriye doğru<br /><br /> Artı İşareti (+)|  
|Uzaklaştır|Geriye dönük CTRL-fare tekerleği<br /><br /> Eksi İşareti (-)|  
|Tasarım yüzeyine yukarı kaydırma|Fare tekerleği geriye doğru<br /><br /> PageDown|  
|Tasarım yüzeyine aşağı kaydırma|Fare tekerleği ileriye doğru<br /><br /> PageUp|  
|Tasarım yüzeyi sola kaydırma|Shift+Fare tekerleği geriye doğru<br /><br /> Fare tekerleği sol<br /><br /> Shift + PageDown|  
|Tasarım yüzeyi sağa kaydırma|Shift+Fare tekerleği ileriye doğru<br /><br /> Fare tekerleği sağ<br /><br /> Shift + PageUp|  
|Klavye odağı başka bir düğüme taşı|Ok tuşları|  
|Klavye odağı (düğüm seçim grubuna ekler) olan düğümü seçin|Shift + Ara çubuğu|  
|Klavye odağı olan düğüm seçimine Değiştir|Ctrl+Ara Çubuğu|  
|Geçerli seçim geçiş (düğüm seçtiyseniz, klavye odağı olan düğümü seçin)|Boşluk çubuğu|  
|Geçerli seçimi Yukarı Taşı|Shift+Yukarı Ok|  
|Geçerli seçim Aşağı Taşı|Shift+Aşağı Ok|  
|Geçerli seçim sola taşı|Shift+Sol Ok|  
|Geçerli seçim sağa taşıyın|Shift + Sağ Ok.|  
  
## <a name="related-topics"></a>İlgili konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Oyunları ve uygulamaları için 3-b varlıklar ile çalışma](../designers/working-with-3-d-assets-for-games-and-apps.md)|Genel bir bakış sağlar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] dokuları ve görüntüleri, 3-b modellere ve gölgelendirici efektleri ile çalışmak için kullanabileceğiniz araçlar.|  
|[Görüntü Düzenleyicisi](../designers/image-editor.md)|Nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] dokuları ve görüntüleri çalışmak için görüntü Düzenleyicisi.|  
|[Model Düzenleyicisi](../designers/model-editor.md)|Nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Model Düzenleyicisi'ni 3-b modelleriyle çalışacak.|