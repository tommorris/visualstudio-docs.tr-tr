---
title: "Gölgelendirici Tasarımcı düğümleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f5192fbd-c78f-40a8-a4d4-443209610268
caps.latest.revision: "6"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2393d254ee2864291a0a3ae5bbed6e78d80d3863
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="shader-designer-nodes"></a>Gölgelendirici Tasarımcısı Düğümleri
Bu bölümdeki makaleleri belgelerin grafik efektler oluşturmak için kullanabileceğiniz çeşitli gölgelendirici Tasarımcısı düğümleri hakkında bilgiler içerir.  
  
## <a name="nodes-and-node-types"></a>Düğüm ve düğüm türleri  
 Gölgelendirici Tasarımcısı görsel efektler bir grafik temsil eder. Bu grafikler, özellikle seçilmiş ve hedeflenen etkileyen elde etmek için kesin yollarla bağlı düğümlerden yerleşik olarak bulunur. Her düğüm bir bilgiyi veya matematik işlevi ve aralarında bağlantı bilgileri sonucu oluşturmak için grafiğin nasıl akacağını temsil eder. Altı farklı düğüm türleri gölgelendirici Tasarımcısı sağlar — filtreleri, doku düğümleri, parametreleri, sabitleri, yardımcı programı düğümleri ve matematik düğümleri — ve birkaç tek düğümler her türe ait. Bu düğüm ve düğüm türleri bu bölümdeki diğer makalelerinde açıklanan — bu belgenin sonundaki bağlantılara bakın.  
  
## <a name="node-structure"></a>Düğümü yapısı  
 Tüm düğümleri ortak öğeler birleşiminden oluşur. Her düğüm (dışında son renk düğümü gölgelendirici çıktısını gösterir), sağ taraftaki en az bir çıkış terminal sahiptir. Hesaplamalar veya doku örnekleyicileri temsil eden düğümleri kendi sol tarafında Terminal giriş ancak hiçbir giriş Terminal bilgileri temsil eden düğümleri sahip. Çıktı Terminal bilgileri bir düğümden diğerine taşımak için Terminal giriş bağlı.  
  
### <a name="promotion-of-inputs"></a>Girdi yükseltme  
 Böylece etkili bir oyun veya uygulama kullanılabilir gölgelendirici Tasarımcısı HLSL kaynak kodu sonuçta oluşturmanız gerekir çünkü gölgelendirici Tasarımcısı düğümleri HLSL kullanan tür yükseltme tabi kurallardır. Grafik donanım öncelikle kayan nokta değerlerine çalıştığından, farklı türler arasında yükseltme yazın; örneğin, `int` için `float`, veya `float` için `double`— nadir bir durumdur. Grafik donanım bilgi aynı anda birden çok parçalarını aynı işlemi kullandığından, bunun yerine, farklı türde bir yükseltme, kısa girişleri sayısının en uzun giriş boyutuna uyacak şekilde uzatılmış ortaya çıkabilir. Nasıl uzatılmış giriş türü ve ayrıca işlemi bağlıdır:  
  
-   **Daha küçük tür bir skaler değere ise:**  
  
     Skaler değeri büyük giriş boyutları eşit olan bir vektör içine çoğaltılır. Örneğin, skaler giriş 5.0 (5.0, 5.0, 5.0) vektör hale işleminin en büyük giriş işlemi ne olursa olsun ek olarak, üç öğesi vektör olduğunda.  
  
-   **Daha küçük bir vektör türüdür ve işlem çarpma (\*, /, % vb.), sonra:**  
  
     Vektör değeri büyük giriş boyutları eşit olan bir vektör başında öğelerini kopyalanır ve sondaki öğeleri 1.0 ayarlanır. Örneğin, vektör giriş (5.0, 5.0) (5.0, 5.0, 1.0, 1.0) vektör hale zaman onu çarpılır dört öğesi vektörü ile. Bu, üçüncü ve dördüncü öğeleri çıkış 1.0 çarpma kimliğini kullanarak korur.  
  
-   **Daha küçük bir vektör türüdür ve işlem toplama (+,-, vb.), sonra:**  
  
     Vektör değeri büyük giriş boyutları eşit olan bir vektör başında öğelerini kopyalanır ve sondaki öğeleri 0,0 olarak ayarlanır. Örneğin, vektör giriş (5.0, 5.0) (5.0, 5.0, 0.0, 0.0) vektör hale onu eklendiğinde dört öğesi vektör için. Bu, üçüncü ve dördüncü öğeleri çıkış 0,0 ADDITIVE kimliğini kullanarak korur.  
  
## <a name="related-topics"></a>İlgili konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Sabit düğüm](../designers/constant-nodes.md)|Değişmez değerler ve gölgelendirici hesaplamalarda Ara değerli köşe durum bilgilerini göstermek için kullanabileceğiniz düğümleri açıklar. Köşe durumu ilişkilendirilir çünkü — ve bu nedenle, her bir piksel için farklı olur — her piksel gölgelendirici örneği sabiti farklı bir sürümünü alır.|  
|[Parametre düğümü](../designers/parameter-nodes.md)|Kamera konumu, malzeme özelliklerine, aydınlatma parametreleri, saat ve diğer uygulama durum bilgilerini gölgelendirici hesaplamalarda temsil etmek için kullanabileceğiniz düğümleri açıklar.|  
|[Doku düğümler](../designers/texture-nodes.md)|Örnek çeşitli doku türleri ve geometri ve üreten veya doku koordinatları yaygın şekilde dönüştürmek için kullanabileceğiniz düğümleri açıklar.|  
|[Matematik düğümler](../designers/math-nodes.md)|Cebirsel gerçekleştirmek için kullanabileceğiniz düğümleri, mantığı, trigonometrik ve doğrudan HLSL yönergeleri eşleme diğer matematik işlemlerini açıklar.|  
|[Yardımcı programı düğümler](../designers/utility-nodes.md)|Ortak aydınlatma hesaplamaları ve doğrudan HLSL yönergeleri eşlemediğinden diğer yaygın işlemler gerçekleştirmek için kullanabileceğiniz düğümleri açıklar.|  
|[Filtre düğümlerinin](../designers/filter-nodes.md)|Doku filtreleme ve renk filtrelemesi gerçekleştirmek için kullanabileceğiniz düğümleri açıklar.|