---
title: Oyunlar ve uygulamalar için 3-b varlıklarla çalışmaya | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
f1_keywords:
- vs.graphics
ms.assetid: 910d673b-c884-4eeb-9928-0e89f3d38cb6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e3b110f5f1a5ecc16d8cafe5f80630da05ed29b8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="working-with-3-d-assets-for-games-and-apps"></a>Oyunlar ve Uygulamalar için 3B Varlıklarla Çalışma
Bu belgede açıklanan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] oluşturmak veya 3-b modelleri, doku ve DirectX tabanlı oyunları ve uygulamaları için gölgelendiriciler değiştirmek için kullanabileceğiniz araçlar.  
  
## <a name="directx-app-development-in-visual-studio"></a>Visual Studio'da DirectX uygulama geliştirme  
 DirectX uygulama programlama mantığı, DirectX API ve zengin ve etkileşimli bir multimedya deneyimi sunmak için ses ve 3-b görsel varlıklar birlikte yüksek düzey gölgeleme dili (HLSL) programlar genellikle birleştirir.[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] başka bir aracı kullanmak için IDE ayrılmadan görüntüleri ve dokuları, 3-b modellere ve gölgelendiriciler ile çalışmak için kullanabileceğiniz araçlar içerir. Visual Studio Araçları oluşturmak için özellikle uygun *yer tutucu* kodu test etmek veya prototipleri üretime hazır varlıklar devreye sokmak önce ve inceleme ve üretime hazır değiştirmek için oluşturmak için kullanabileceğiniz varlıklar Uygulamanızı ayıklarken varlıklar.  
  
 İle çalışmak varlıklar türleri hakkında daha fazla bilgi aşağıdadır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
### <a name="images-and-textures"></a>Görüntüleri ve dokuları  
 Görüntüleri ve dokuları renk ve oyunları ve uygulamaları visual ayrıntı sağlar. 3B grafik dokuları çeşitli biçimleri, türleri ve geometri farklı kullanımlarını gelir. Örneğin, normal eşlemeleri, 3-b modellerin aydınlatma daha ayrıntılı piksel başına yüzey normalleri sağlar ve küp eşlemeleri sky kutulama, yansımaları ve küresel doku eşleme gibi kullanımlar için tüm yönde doku sağlar. Dokular farklı ayrıntı düzeyleri en verimli oluşturma desteklemek için MIP eşlemeleri sağlayabilir ve farklı bir renk kanalları ve renk sıralamalarını destekleyebilir. Dokular çeşitli daha az ayrılmış grafik belleği kaplar ve Gpu'lara erişim dokuları daha verimli bir şekilde yardım eden sıkıştırılmış biçimlerinde depolanabilir.  
  
 Kullanabileceğiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] görüntüler ve pek çok yaygın türlerini ve biçimlerini dokular çalışmak için görüntü Düzenleyicisi.  
  
### <a name="3-d-models"></a>3B modeller  
 3-b modellerini oyunları ve uygulamaları alan ve şekil oluşturun. En azından modelleri 3B noktaları konumunu kodlamak — olarak bilinen *köşeleri*— çizgi veya model şekli temsil üçgenler tanımlamak için veri dizine birlikte. Ek veriler bu köşeleri ile ilişkili olabilir — örneğin, bilgileri, normal vektörlerinin veya uygulamaya özel öznitelikleri rengi. Her model nesnesi genelinde öznitelikler de tanımlayabilirsiniz — Örneğin, hangi gölgelendirici nesnenin yüzey veya hangi doku uygulandığı görünümünü hesaplamak için kullanılır.  
  
 Kullanabileceğiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Model Düzenleyicisi'ni 3-b ile çalışmak için birkaç ortak biçimlerde modeller.  
  
### <a name="shaders"></a>Gölgelendiriciler  
 Gölgelendiriciler grafik işlemci birimi (GPU) çalıştırmak, etki alanına özgü küçük programlardır. Gölgelendiriciler belirlemek nasıl 3-b modellere içine ekran dönüştürüldüğünden şekilleri ve bu şekillerde her piksel nasıl renkli. Gölgelendirici oluşturma ve oyun veya uygulama bir nesneye uygulayarak, benzersiz bir görünüm nesnesi verebilirsiniz.  
  
 Kullanabileceğiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] gölgelendirici bir grafik tabanlı gölgelendirici tasarım aracı olan özel görsel efektler HLSL programlama bilmeden oluşturmak üzere Tasarımcısı,.  
  
> [!NOTE]
>  DirectX programlama ile başlatma hakkında daha fazla bilgi için bkz: [DirectX](http://go.microsoft.com/fwlink/p/?LinkId=224633). DirectX tabanlı bir uygulamanın hata ayıklama hakkında daha fazla bilgi için bkz: [grafik tanılama (DirectX grafikleri hata ayıklama)](../debugger/visual-studio-graphics-diagnostics.md).  
  
## <a name="directx-version-compatibility"></a>DirectX sürümü uyumluluğu  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] DirectX 2 ve 3 boyutlu varlıkları işlemek için kullanır. DirectX 11 Oluşturucu ya da Windows Gelişmiş Tarama Platform (TÜNELİ) yazılım oluşturucusu seçebilirsiniz. DirectX 11 Oluşturucu DirectX 11 ve DirectX 10 GPU yüksek performanslı, donanım hızlandırılmış işleme sağlar. TÜNELİ Oluşturucu varlıklarınızı çok çeşitli bilgisayarlar çalışma emin olmaya yardımcı olur — bu modern grafik donanım olmayan bilgisayarları ve grafik donanımı tümleşik bilgisayarları içerir. TÜNELİ hakkında daha fazla bilgi için bkz: [Windows Gelişmiş Tarama Platform (TÜNELİ) Kılavuzu](http://go.microsoft.com/fwlink/p/?LinkId=224634).  
  
## <a name="related-topics"></a>İlgili konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Dokularla ve Görüntülerle Çalışma](../designers/working-with-textures-and-images.md)|Nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] görüntüleri ve dokuları çalışmak için.|  
|[3B Modelleriyle Çalışma](../designers/working-with-3-d-models.md)|Nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 3-b modelleriyle çalışacak.|  
|[Gölgelendiricilerle Çalışma](../designers/working-with-shaders.md)|Nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] gölgelendirici Designer'ın oluşturabilir ve özel gölgelendirici etkileri değiştirebilirsiniz.|  
|[Oyunlarda veya Uygulamalarda 3B Varlıklar Kullanma](../designers/using-3-d-assets-in-your-game-or-app.md)|Görüntü Düzenleyicisi, Model Düzenleyicisinde veya gölgelendirici Tasarımcısı oyun ya da uygulama kullanılarak oluşturulan varlıklar kullanmayı açıklar.|