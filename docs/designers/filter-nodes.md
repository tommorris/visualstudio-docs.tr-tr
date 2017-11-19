---
title: "Düğümleri filtreleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7cae2dc-e9a7-49d4-8be5-58b79868624e
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b11e18af13cc0fc60812a036174c52105ac08a7d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="filter-nodes"></a>Filtre Düğümleri
Gölgelendirici Tasarımcısı'nda giriş filtre düğümlerinin dönüştürme — Örneğin, bir renk veya doku örnek — içine mecazi renk değeri. Bu mecazi renk değerleri, fotoğraf kalitesinde olmayan işleme veya diğer görsel efektler bileşen olarak yaygın olarak kullanılır.  
  
## <a name="filter-node-reference"></a>Filtre düğümü başvurusu  
  
|Düğüm|Ayrıntılar|Özellikler|  
|----------|-------------|----------------|  
|**Ölçeklendirilmelidir**|Piksel cinsinden bir doku Gauss işlevini kullanarak bulanıklaştırır.<br /><br /> Bu renk ayrıntı ya da bir doku gürültü azaltmak için kullanabilirsiniz.<br /><br /> **Giriş:**<br /><br /> `UV`: `float2`<br /> Test etmek için texel koordinatları.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float4`<br /> Bulanık renk değeri.|**Doku**<br /> Bulanıklaştırma sırasında kullanılan örneği ile ilişkili doku kaydedin.|  
|**Doygunluğu Azalt**|Belirtilen renk renkte miktarını azaltır.<br /><br /> Renk kaldırılmış olarak renk değeri gri tonlamalı karşılığını yaklaşıyor.<br /><br /> **Giriş:**<br /><br /> `RGB`: `float3`<br /> Doygunluğu Azalt rengi.<br /><br /> `Percent`: `float`<br /> Kaldırmak için renk yüzdesi ifade [0, 1] aralığında normalleştirilmiş değeri olarak.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float3`<br /> Doygunluğu azaltılmış rengi.|**Aydınlatma**<br /> Kırmızı, yeşil ve mavi renk bileşenleri verilen ağırlıkları.|  
|**Kenar algılama**|Kenarları Canny kenar algılayıcısı kullanarak dokuyu algılar. Kenar piksel beyaz olarak çıkışıdır; Kenar olmayan piksel siyah olarak çıkışıdır.<br /><br /> Kenar piksel işlemek için ek efektler kullanabilmeleri doku kenarları tanımlamak için bunu kullanabilirsiniz.<br /><br /> **Giriş:**<br /><br /> `UV`: `float2`<br /> Test etmek için texel koordinatları.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float4`<br /> Texel bir kenarına ise beyaz; Aksi takdirde, siyah.|**Doku**<br /> Kenar algılama sırasında kullanılan örneği ile ilişkili doku kaydedin.|  
|**Keskinleştirme**|Bir doku keskinleştirir.<br /><br /> İyi bir doku Ayrıntılar vurgulamak için bunu kullanabilirsiniz.<br /><br /> **Giriş:**<br /><br /> `UV`: `float2`<br /> Test etmek için texel koordinatları.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float4`<br /> Bulanık renk değeri.|**Doku**<br /> Keskinleştirme sırasında kullanılan örneği ile ilişkili doku kaydedin.|