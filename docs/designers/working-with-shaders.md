---
title: Gölgelendiricilerle Çalışma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 6b2ea1ed-b995-4e75-af19-c68fd37a3bc5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b0c42b90998eef8314f37060b655185d1c68b53b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31925366"
---
# <a name="work-with-shaders"></a>Gölgelendiriciler ile çalışma

Visual Studio'da tasarım özel gölgelendirici efektler gölgelendirici grafik tabanlı Tasarımcısı'nı kullanabilirsiniz. DirectX tabanlı oyun veya uygulama bu gölgelendiriciler kullanabilirsiniz.

## <a name="shaders"></a>Gölgelendiriciler

A *gölgelendirici* grafik hesaplamaları gerçekleştiren bir bilgisayarda program — Örneğin, köşe dönüşümleri veya piksel renklendirme — ve genellikle CPU yerine bir grafik işlemci birimi (GPU) çalışır. Çoğu geleneksel, sabit işlevi grafik ardışık düzen aşamaları şimdi gölgelendirici programlar tarafından gerçekleştirildiğinden, uygulamanızın ihtiyaçları için özel bir işlem hattı oluşturmak için kullanabilirsiniz.

En yaygın gölgelendiriciler türleridir *köşe gölgelendiriciler*, köşe başına hesaplamalar ve sabit işlev dönüştürme ve Aydınlatma devresi programlanabilir olmayan grafik donanımda değiştirin ve *piksel Gölgelendiriciler*, bir piksel rengini belirlemek ve programlanabilir olmayan grafik donanımda sabit işlevi renk-Birleştirici devresi Değiştir piksel başına hesaplamalar gerçekleştirin. Modern grafik donanım yaptı gölgelendiriciler daha da fazla türde olası —*hull gölgelendiriciler*, *etki alanı gölgelendiriciler*, ve *geometri gölgelendiriciler* grafik hesaplamaları ve *gölgelendiriciler işlem* grafik olmayan hesaplamalar için. Bu aşamalar hiçbiri programlanabilir olmayan grafik donanımda bile kullanılabilir. Gölgelendiriciler başlangıçta verileri paralel (SIMD) ve grafik merkezli (nokta ürün) yönergeleri sağlanan bir derleme benzeri bir dil kullanılarak oluşturulmuş. Şimdi, gölgelendiriciler genellikle HLSL (yüksek düzey gölgelendirici dili) gibi üst düzey, C benzeri diller kullanılarak oluşturulur.

Etkileşimli bir şekilde yerine, piksel gölgelendiriciler girme ve kod derleme oluşturmak için gölgelendirici Tasarımcısı'nı kullanabilirsiniz. Gölgelendirici Tasarımcısı'nda gölgelendirici veri ve işlemleri ve veri değerlerinin akışı temsil eden düğümleri ve Ara sonuçların gölgelendirici aracılığıyla arasındaki bağlantıları temsil eden düğüm sayısı tarafından tanımlanır. Bu yaklaşım ve gerçek zamanlı Önizleme gölgelendirici Tasarımcısı'nda kullanarak gölgelendirici yürütülmesi daha kolay görselleştirmek ve "deneme aracılığıyla ilginç gölgelendirici Çeşitlemeler Bul".

## <a name="dgsl-documents"></a>DGSL belgeleri

Gölgelendirici Tasarımcısı gölgelendiriciler yönlendirilmiş grafik biçimlendirme dili (DGML üzerinde) temel bir XML biçimi yönlendirilmiş grafik gölgelendirici dili (DGSL) biçiminde kaydeder. 3B modeller Model Düzenleyicisi'nde için doğrudan DGSL gölgelendiriciler uygulayabilirsiniz. Uygulamanızda DGSL gölgelendirici kullanmadan önce ancak bunu DirectX özelliğini algılayan bir biçimine dışa aktarmanız gerekir — Örneğin, HLSL.

DGSL DGML ile uyumlu olduğundan DGSL gölgelendiriciler çözümlemek için DGML belgeleri çözümlemek için tasarlanmış araçları kullanabilirsiniz. DGML hakkında daha fazla bilgi için bkz: [anlama yönlendirilmiş grafik biçimlendirme dili (DGML)](http://msdn.microsoft.com/library/ee842619.aspx).

## <a name="related-topics"></a>İlgili konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Gölgelendirici Tasarımcısı](../designers/shader-designer.md)|Visual Studio gölgelendirici Tasarımcısı gölgelendiriciler ile çalışmak için nasıl kullanılacağını açıklar.|
|[Gölgelendirici Tasarımcısı Düğümleri](../designers/shader-designer-nodes.md)|Grafik efektleri elde etmek için kullanabileceğiniz gölgelendirici Tasarımcısı düğüm türleri açıklanmaktadır.|
|[Gölgelendirici Tasarımcısı Örnekleri](../designers/shader-designer-examples.md)|Gölgelendirici Tasarımcısı genel grafik etkileri elde etmek için nasıl kullanılacağını gösteren konulara bağlantılar sağlar.|