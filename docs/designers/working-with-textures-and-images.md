---
title: Dokular ve görüntüleri ile çalışma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
ms.assetid: b9fbc8fa-66d1-4055-8460-24d8b8fbe43e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 148732e45dc839a30e60586de594d6b62fda16a8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="working-with-textures-and-images"></a>Dokularla ve Görüntülerle Çalışma
Görüntü Düzenleyicisi'nde kullanabileceğiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] dokuları ve görüntüleri oluşturmak ve değiştirmek için. Görüntü Düzenleyicisi DirectX uygulaması geliştirme Kullanılanlara gibi zengin doku ve görüntü biçimlerini destekler.  
  
> [!NOTE]
>  Görüntü Düzenleyicisi simgeler veya imleçler gibi düşük Renk görüntülerini desteklemiyor. Oluşturmak veya bu görüntüleri türlerini değiştirmek için kullanmak [simgeler için görüntü Düzenleyicisi](/cpp/windows/image-editor-for-icons).  
  
## <a name="textures-and-images"></a>Dokular ve görüntüleri  
 Dokular ve görüntüleri, temel düzeyde, yalnızca tablolar Grafik uygulamalarında visual ayrıntı sağlamak için kullanılan veri var. Nasıl kullanıldığı hakkında bir doku veya görüntü sağlar ayrıntı tür bağlıdır, ancak renk örnekleri, alfa (Saydamlık) değerleri, yüzey normalleri ve yükseklik değerleri yaygın olarak gösterilebilir. Bir doku şekli bir gösterimi ile birlikte kullanılmak üzere tasarlanmıştır ve görüntüyü bir doku arasındaki birincil fark olan — tipik bir 3B modelin — eksiksiz bir nesneyi veya Sahne ancak görüntüyü ifade etmek için genellikle bir tek başına nesne veya Sahne gösterimidir .  
  
 Dokular ortak türleri şunlardır:  
  
 Doku eşlemeleri  
 Doku eşlemleri bir tane, iki veya üç boyutlu matris düzenlenmiş renk değerleri içerir. Bunlar, etkilenen bir nesne üzerinde renk ayrıntı sağlamak için kullanılır. Renkleri (kırmızı, yeşil, mavi) RGB renk kanalları kullanılarak yaygın olarak kodlanır ve dördüncü içerebilir saydamlık temsil eden kanal, alfa,. Daha az yaygın olarak, renkler başka bir renk şeması kodlanmış veya dördüncü kanal alfa dışında veri içeriyor olabilir — örneğin, yükseklik.  
  
 Normal eşlemeleri  
 Normal eşlemeleri yüzey normalleri içerir. Bunlar, etkilenen bir nesne üzerinde aydınlatma ayrıntı sağlamak için kullanılır. Normalleri x, y ve z boyutlarını vektör depolamak için kırmızı, yeşil ve mavi renk bileşenlerini kullanarak yaygın olarak kodlanır. Ancak, diğer Kodlamalar mevcut — Örneğin, Kutupsal koordinatlarına göre kodlaması.  
  
 Yükseklik eşlemeleri  
 Yükseklik eşlemeleri yükseklik alan verileri içerir. Etkilenen bir nesne üzerinde bir form geometrik ayrıntı sağlamak için kullanılan — istenilen efekti hesaplamak için gölgelendirici kodu kullanarak — veya terrain oluşturma gibi kullanımlar için veri noktaları sağlar. Yükseklik değerleri, genellikle bir doku bir kanalı kullanılarak kodlanır.  
  
 Küp eşlemeleri  
 Küp eşlemeleri, farklı veri türlerini içerebilir — Örneğin, renkleri veya normalleri — bir küp yüzeyleri altı doku olarak düzenlenmiş ancak. Bu nedenle, küp eşlemeleri doku koordinatları sağlayarak örneklenen değil, ancak bir vektör sağlayarak, kaynak küp merkezidir; Örnek vektör küp kesiştiği noktayı alınır. Küp eşlemeleri yaklaşık yansımaları hesaplamak için kullanılan ortamı sağlamak için kullanılır; bu olarak bilinir *ortam eşleme*— veya küresel nesnelere doku temel, daha az bozulma sağlamak için iki boyutlu dokular sağlayabilir.  
  
 Tüm doku kodlanmış ve bir doku tutan veri ya da boyut türüyle resme çeşitli yollarla veya doku "şeklini" sıkıştırılmış. Ancak, farklı kodlama ve sıkıştırma yöntemleri daha iyi farklı veri türleri için sonuçlar.  
  
 Dokular ve diğer görüntü düzenleyicilerde benzer şekilde görüntülerini oluşturmak ve değiştirmek için görüntü Düzenleyicisi'ni kullanabilirsiniz. Görüntü Düzenleyicisi ayrıca 3B grafik ile kullanılmak üzere mipmap oluşturma ve diğer özellikleri sağlar ve DirectX desteklediği yüksek oranda sıkıştırılmış, donanım hızlandırılmış doku biçimlerini çoğunu destekler.  
  
## <a name="related-topics"></a>İlgili konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Görüntü Düzenleyicisi](../designers/image-editor.md)|Görüntü Düzenleyicisi dokuları ve görüntüleri ile çalışmak için nasıl kullanılacağını açıklar.|  
|[Görüntü Düzenleyicisi Örnekleri](../designers/image-editor-examples.md)|Görüntü Düzenleyicisi ortak görüntü işleme görevlerini gerçekleştirmek için nasıl kullanılacağını gösteren konulara bağlantılar sağlar.|