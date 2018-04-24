---
title: 3B varlıklarıyla oyunları ve uygulamaları için çalışma
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
f1_keywords:
- vs.graphics
ms.assetid: 910d673b-c884-4eeb-9928-0e89f3d38cb6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cd99cad3b63df1cf7ab3bcecb347df53f7408832
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="work-with-3d-assets-for-games-and-apps"></a>3B varlıklarla oyunları ve uygulamaları için çalışın

Bu belgeyi oluşturmak veya 3B modelleri, doku ve DirectX tabanlı oyunları ve uygulamaları için gölgelendiriciler değiştirmek için kullanabileceğiniz Visual Studio Araçları açıklar.

## <a name="directx-app-development-in-visual-studio"></a>Visual Studio'da DirectX uygulama geliştirme
 DirectX uygulama programlama mantığı, DirectX API ve zengin ve etkileşimli bir multimedya deneyimi sunmak için ses ve 3B görsel varlıklar birlikte yüksek düzey gölgeleme dili (HLSL) programlar genellikle birleştirir. Visual Studio başka bir aracı kullanmak için IDE ayrılmadan görüntüleri ve dokuları, 3B modeller ve gölgelendiriciler ile çalışmak için kullanabileceğiniz araçlar içerir. Visual Studio Araçları oluşturmak için özellikle uygun *yer tutucu* kodu test etmek veya prototipleri üretime hazır varlıklar devreye sokmak önce ve inceleme ve üretime hazır değiştirmek için oluşturmak için kullanabileceğiniz varlıklar Uygulamanızı ayıklarken varlıklar.

 Visual Studio'da çalışabilirsiniz varlıklar türleri hakkında daha fazla bilgi aşağıdadır.

### <a name="images-and-textures"></a>Görüntüleri ve dokuları
 Görüntüleri ve dokuları renk ve oyunları ve uygulamaları visual ayrıntı sağlar. 3B grafik dokuları çeşitli biçimleri, türleri ve geometri farklı kullanımlarını gelir. Örneğin, normal eşlemeleri, 3B modellerin aydınlatma daha ayrıntılı piksel başına yüzey normalleri sağlar ve küp eşlemeleri sky kutulama, yansımaları ve küresel doku eşleme gibi kullanımlar için tüm yönde doku sağlar. Dokular farklı ayrıntı düzeyleri en verimli oluşturma desteklemek için MIP eşlemeleri sağlayabilir ve farklı bir renk kanalları ve renk sıralamalarını destekleyebilir. Dokular çeşitli daha az ayrılmış grafik belleği kaplar ve Gpu'lara erişim dokuları daha verimli bir şekilde yardım eden sıkıştırılmış biçimlerinde depolanabilir.

 Görüntüleri ve pek çok yaygın türlerini ve biçimlerini dokular çalışmak için Visual Studio görüntü Düzenleyicisi'ni kullanabilirsiniz.

### <a name="3d-models"></a>3B modelleri
 3B modeller oyunları ve uygulamaları alan ve şekil oluşturun. En azından modelleri 3B uzaydaki noktaları konumunu kodlamak — olarak bilinen *köşeleri*— çizgi veya model şekli temsil üçgenler tanımlamak için veri dizine birlikte. Ek veriler bu köşeleri ile ilişkili olabilir — örneğin, bilgileri, normal vektörlerinin veya uygulamaya özel öznitelikleri rengi. Her model nesnesi genelinde öznitelikler de tanımlayabilirsiniz — Örneğin, hangi gölgelendirici nesnenin yüzey veya hangi doku uygulandığı görünümünü hesaplamak için kullanılır.

 Ortak çeşitli biçimlerde 3B modelleri ile çalışmak için Visual Studio Model Düzenleyicisi'ni kullanın.

### <a name="shaders"></a>Gölgelendiriciler
 Gölgelendiriciler grafik işlemci birimi (GPU) çalıştırmak, etki alanına özgü küçük programlardır. Gölgelendiriciler belirlemek 3B modellerin içine ekran dönüştürüldüğünden şekilleri ve bu şekillerde her piksel nasıl renkli. Gölgelendirici oluşturma ve oyun veya uygulama bir nesneye uygulayarak, benzersiz bir görünüm nesnesi verebilirsiniz.

 HLSL programlama bilmeden özel görsel efektler oluşturmak için Visual Studio gölgelendirici bir grafik tabanlı gölgelendirici tasarım aracı olan Tasarımcısı, kullanabilirsiniz.

> [!NOTE]
> DirectX programlama ile başlatma hakkında daha fazla bilgi için bkz: [DirectX](http://go.microsoft.com/fwlink/p/?LinkId=224633). DirectX tabanlı bir uygulamanın hata ayıklama hakkında daha fazla bilgi için bkz: [grafik tanılama (DirectX grafikleri hata ayıklama)](../debugger/visual-studio-graphics-diagnostics.md).

## <a name="directx-version-compatibility"></a>DirectX sürümü uyumluluğu
 Visual Studio DirectX 2B ve 3B varlıkları işlemek için kullanır. DirectX 11 Oluşturucu ya da Windows Gelişmiş Tarama Platform (TÜNELİ) yazılım oluşturucusu seçebilirsiniz. DirectX 11 Oluşturucu DirectX 11 ve DirectX 10 GPU yüksek performanslı, donanım hızlandırılmış işleme sağlar. TÜNELİ Oluşturucu varlıklarınızı çok çeşitli bilgisayarlar çalışma emin olmaya yardımcı olur — bu modern grafik donanım olmayan bilgisayarları ve grafik donanımı tümleşik bilgisayarları içerir. TÜNELİ hakkında daha fazla bilgi için bkz: [Windows Gelişmiş Tarama Platform (TÜNELİ) Kılavuzu](http://go.microsoft.com/fwlink/p/?LinkId=224634).

## <a name="related-topics"></a>İlgili konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Dokularla ve Görüntülerle Çalışma](../designers/working-with-textures-and-images.md)|Görüntüleri ve dokuları çalışmak için Visual Studio kullanmayı açıklar.|
|[3B modeller ile çalışma](../designers/working-with-3-d-models.md)|Visual Studio çalışma 3B modelleri ile çalışmak için nasıl kullanılacağını açıklar.|
|[Gölgelendiricilerle Çalışma](../designers/working-with-shaders.md)|Visual Studio gölgelendirici Tasarımcısı oluşturup özel gölgelendirici efektleri değiştirmek için nasıl kullanılacağını açıklar.|
|[Oyun veya uygulama 3B varlıkları kullanma](../designers/using-3-d-assets-in-your-game-or-app.md)|Görüntü Düzenleyicisi, Model Düzenleyicisinde veya gölgelendirici Tasarımcısı oyun ya da uygulama kullanılarak oluşturulan varlıklar kullanmayı açıklar.|