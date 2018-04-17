---
title: Gölgelendiriciler ile çalışma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
ms.assetid: 6b2ea1ed-b995-4e75-af19-c68fd37a3bc5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d9fae275bde5ecfe5a2f359c82519d1e9a8f6eb6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="working-with-shaders"></a>Gölgelendiricilerle Çalışma
Grafik tabanlı gölgelendirici Tasarımcısı'nda kullanabileceğiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tasarımı özel gölgelendirici etkilerini için. DirectX tabanlı oyun veya uygulama bu gölgelendiriciler kullanabilirsiniz.  
  
## <a name="shaders"></a>Gölgelendiriciler  
 A *gölgelendirici* grafik hesaplamaları gerçekleştiren bir bilgisayarda program — Örneğin, köşe dönüşümleri veya piksel renklendirme — ve genellikle CPU yerine bir grafik işlemci birimi (GPU) çalışır. Çoğu geleneksel, sabit işlevi grafik ardışık düzen aşamaları şimdi gölgelendirici programlar tarafından gerçekleştirildiğinden, uygulamanızın ihtiyaçları için özel bir işlem hattı oluşturmak için kullanabilirsiniz.  
  
 En yaygın gölgelendiriciler türleridir *köşe gölgelendiriciler*, köşe başına hesaplamalar ve sabit işlev dönüştürme ve Aydınlatma devresi programlanabilir olmayan grafik donanımda değiştirin ve *piksel Gölgelendiriciler*, bir piksel rengini belirlemek ve programlanabilir olmayan grafik donanımda sabit işlevi renk-Birleştirici devresi Değiştir piksel başına hesaplamalar gerçekleştirin. Modern grafik donanım yaptı gölgelendiriciler daha da fazla türde olası —*hull gölgelendiriciler*, *etki alanı gölgelendiriciler*, ve *geometri gölgelendiriciler* grafik hesaplamaları ve *gölgelendiriciler işlem* grafik olmayan hesaplamalar için. Bu aşamalar hiçbiri programlanabilir olmayan grafik donanımda bile kullanılabilir. Gölgelendiriciler başlangıçta verileri paralel (SIMD) ve grafik merkezli (nokta ürün) yönergeleri sağlanan bir derleme benzeri bir dil kullanılarak oluşturulmuş. Şimdi, gölgelendiriciler genellikle HLSL (yüksek düzey gölgelendirici dili) gibi üst düzey, C benzeri diller kullanılarak oluşturulur.  
  
 Etkileşimli bir şekilde yerine, piksel gölgelendiriciler girme ve kod derleme oluşturmak için gölgelendirici Tasarımcısı'nı kullanabilirsiniz. Gölgelendirici Tasarımcısı'nda gölgelendirici veri ve işlemleri ve veri değerlerinin akışı temsil eden düğümleri ve Ara sonuçların gölgelendirici aracılığıyla arasındaki bağlantıları temsil eden düğüm sayısı tarafından tanımlanır. Bu yaklaşım ve gerçek zamanlı Önizleme gölgelendirici Tasarımcısı'nda kullanarak gölgelendirici yürütülmesi daha kolay görselleştirmek ve "deneme aracılığıyla ilginç gölgelendirici Çeşitlemeler Bul".  
  
## <a name="dgsl-documents"></a>DGSL belgeleri  
 Gölgelendirici Tasarımcısı gölgelendiriciler yönlendirilmiş grafik biçimlendirme dili (DGML üzerinde) temel bir XML biçimi yönlendirilmiş grafik gölgelendirici dili (DGSL) biçiminde kaydeder. 3-b modelleri Model Düzenleyicisi'nde için doğrudan DGSL gölgelendiriciler uygulayabilirsiniz. Uygulamanızda DGSL gölgelendirici kullanmadan önce ancak bunu DirectX özelliğini algılayan bir biçimine dışa aktarmanız gerekir — Örneğin, HLSL.  
  
 DGSL DGML ile uyumlu olduğundan DGSL gölgelendiriciler çözümlemek için DGML belgeleri çözümlemek için tasarlanmış araçları kullanabilirsiniz. DGML hakkında daha fazla bilgi için bkz: [anlama yönlendirilmiş grafik biçimlendirme dili (DGML)](http://msdn.microsoft.com/library/ee842619.aspx).  
  
## <a name="related-topics"></a>İlgili konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Gölgelendirici Tasarımcısı](../designers/shader-designer.md)|Nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] gölgelendirici Designer'ın gölgelendiriciler ile çalışır.|  
|[Gölgelendirici Tasarımcısı Düğümleri](../designers/shader-designer-nodes.md)|Grafik efektleri elde etmek için kullanabileceğiniz gölgelendirici Tasarımcısı düğüm türleri açıklanmaktadır.|  
|[Gölgelendirici Tasarımcısı Örnekleri](../designers/shader-designer-examples.md)|Gölgelendirici Tasarımcısı genel grafik etkileri elde etmek için nasıl kullanılacağını gösteren konulara bağlantılar sağlar.|