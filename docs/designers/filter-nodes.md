---
title: Düğümleri filtreleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
ms.assetid: f7cae2dc-e9a7-49d4-8be5-58b79868624e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2b1b27feacee7aee57b773d78b3680bef6b99567
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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