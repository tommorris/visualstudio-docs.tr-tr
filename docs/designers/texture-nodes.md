---
title: "Doku düğümleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b7df5ef3-dd4f-4964-9d96-34e0e180515e
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: df87a8c890f5326e4b7b385016e17a432626ec92
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="texture-nodes"></a>Doku Düğümleri
Gölgelendirici Tasarımcısı'nda dokuyu düğümlerin örnek çeşitli doku türleri ve geometri ve üreten veya doku koordinatları Dönüştür. Dokular renk ve ayrıntı nesnelerde ışık sağlar.  
  
## <a name="texture-node-reference"></a>Doku düğümü başvurusu  
  
|Düğüm|Ayrıntılar|Özellikler|  
|----------|-------------|----------------|  
|**Cubemap örnek**|Bir cubemap renk örnekten belirtilen koordinatlarda alır.<br /><br /> Yansıma efektler için renk ayrıntı sağlamak için ya da bir 2B doku daha az bozulma sahip bir doku küresel bir nesneye uygulamak için bir cubemap kullanabilirsiniz.<br /><br /> **Giriş:**<br /><br /> `UVW`: `float3`<br /> Burada örnek alındıktan doku küp konumu belirtir vektörü. Örnek bu vektörü küp kesiştiği alınır.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float4`<br /> Renk örneği.|**Doku**<br /> Örneği ile ilişkili doku kaydedin.|  
|**Normal eşleme örneği**|2-D normal bir eşlem normal bir örnekten belirtilen koordinatlarda alır<br /><br /> Bir nesnenin yüzeyinde ek geometrik ayrıntı görünümünü benzetimini yapmak için normal bir harita kullanabilirsiniz. Birim vektör yerine renk verilerini temsil eden paketlenmiş verileri normal eşlemeleri içeren<br /><br /> **Giriş:**<br /><br /> `UV`: `float2`<br /> Burada örnek alındıktan koordinatları.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float3`<br /> Normal örnek.|**Eksen ayarlama**<br /> Normal harita örneğindeki el kullanımı ayarlamak için kullanılan faktörü.<br /><br /> **Doku**<br /> Örneği ile ilişkili doku kaydedin.|  
|**PAN UV**|Planlar süresinin bir işlevi olarak belirtilen doku düzenler.<br /><br /> Bir doku veya normal eşlem nesneyi yüzeyde taşımak için bunu kullanabilirsiniz.<br /><br /> **Giriş:**<br /><br /> `UV`: `float2`<br /> PAN koordinatları.<br /><br /> `Time`: `float`<br /> Süreyi saniye cinsinden, kaydırmak için.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float2`<br /> Panned koordinatları.|**X hızı**<br /> Saniye başına x ekseni boyunca yatay olarak kaydırıldığında texels sayısı.<br /><br /> **Y hızı**<br /> Saniye başına y ekseni boyunca yatay olarak kaydırıldığında texels sayısı.|  
|**Parallax UV**|Belirtilen doku koordinatları yükseklik ve görüntüleme açı bir işlevi olarak değiştirileceğini.<br /><br /> Bu oluşturur etkili olarak bilinen *parallax eşleme*, veya sanal öteleme eşlemesi. Düz bir yüzey üzerinde bir derinliği atmosferini oluşturmak için kullanabilirsiniz.<br /><br /> **Giriş:**<br /><br /> `UV`: `float2`<br /> Yerini koordinatları.<br /><br /> `Height`: `float`<br /> İle ilişkili heightmap değeri `UV` koordinatları.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float2`<br /> Hatalı yerleştirilen koordinatları.|**Derinlik düzlemi**<br /> Parallax etkisi referans derinliği. Varsayılan değer 0,5 ' dir. Küçük değerler doku kaldırın; daha büyük değerler yüzeye havuzu.<br /><br /> **Derinlik ölçek**<br /> Parallax etkisi ölçeğini. Bu görünen derinliği fazla veya az belirgin hale getirir. Tipik değerleri 0,02 ile arasında 0,1.|  
|**UV Döndür**|Belirtilen doku koordinatları merkezi bir nokta çevresinde süresinin bir işlevi olarak döndürür.<br /><br /> Bir doku veya nesnenin yüzeyinde normal Haritası döndürme için bunu kullanabilirsiniz.<br /><br /> **Giriş:**<br /><br /> `UV`: `float2`<br /> Döndürmek için koordinatları.<br /><br /> `Time`: `float`<br /> Süreyi saniye cinsinden, kaydırmak için.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float2`<br /> Döndürülen koordinatları.|**Merkezi X**<br /> Dönüş merkezini tanımlar x koordinatı.<br /><br /> **Merkezi Y**<br /> Dönüş merkezini tanımlar y koordinatı.<br /><br /> **Hızı**<br /> Radyan cinsinden açıdır, saniye başına doku döndüğü tarafından.|  
|**Doku koordinat**|Geçerli piksel doku koordinatları.<br /><br /> Doku koordinatları yakındaki köşeleri Doku koordinat öznitelikleri arasında enterpolasyonla tarafından belirlenir. Bu geçerli piksel doku alanı konumu olarak düşünebilirsiniz.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float2`<br /> Doku koordinatları.|Yok.|  
|**Doku boyutları**|Genişlik ve yükseklik 2B doku eşleme çıkarır.<br /><br /> Genişlik ve yükseklik gölgelendirici dokuyu dikkate alınması gereken doku boyutları kullanabilirsiniz.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float2`<br /> Genişlik ve yükseklik vektör olarak ifade edilen dokuyu. Genişlik vektör ilk öğe depolanır. İkinci öğe yüksekliği depolanır.|**Doku**<br /> Doku boyutlarda ilişkili doku kaydedin.|  
|**Texel Delta**|2-D eşlemi texels arasında (uzaklık) delta çıkarır.<br /><br /> Texel delta gölgelendirici komşu texel değerlerde örneklemek için kullanabilirsiniz.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float2`<br /> Delta (uzaklık) bir texel normalleştirilmiş doku alanda vektör olarak ifade edilen (çapraz pozitif yönde taşıma) sonraki texel için. Tüm komşu texels konumlarını seçmeli olarak yoksayılıyor veya delta U veya V koordinatlarını negating türetilemeyeceğini.|**Doku**<br /> Texel delta ile ilişkili doku kaydedin.|  
|**Doku örnek**|2-D eşlemi renk örnekten belirtilen koordinatlarda alır.<br /><br /> Bir doku eşlemi nesneyi yüzey üzerinde renk ayrıntı sağlamak için kullanabilirsiniz.<br /><br /> **Giriş:**<br /><br /> `UV`: `float2`<br /> Burada örnek alındıktan koordinatları.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float4`<br /> Renk örneği.|**Doku**<br /> Örneği ile ilişkili doku kaydedin.|