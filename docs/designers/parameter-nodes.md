---
title: "Parametre düğümü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da54db0b-3a3d-48dc-858c-7ac43aa04b13
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6c93a889ca1bfa911a9f0934302450f6c1ec5413
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="parameter-nodes"></a>Parametre Düğümleri
Gölgelendirici Tasarımcısı'nda uygulama denetimi çizim başına temelinde, örneğin: Gölgelendirici, malzeme özellikleri, tek yönlü ışık, kamera konumunu ve zaman girişleri parametre düğümü temsil eder. Bu parametrelerin her çizim çağrıyla değişebildiğinden, nesnenin farklı görünümleri vermek için aynı gölgelendirici kullanabilirsiniz.  
  
## <a name="parameter-node-reference"></a>Parametre düğüm başvurusu  
  
|Düğüm|Ayrıntılar|Özellikler|  
|----------|-------------|----------------|  
|**Kamera World konumu**|Dünya alanı kamera konumu.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float4`<br /> Kamera konumu.|Yok.|  
|**Hafif yönü**|Açık, dünya uzayındaki ışık kaynağından dönüştürüldüğüne yönü tanımlar vektörü.<br /><br /> Dünya alanı aydınlatma ve aynasal katkı hesaplamak için bunu kullanabilirsiniz.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float3`<br /> Geçerli piksel öğesinden ışık kaynağına.|Yok.|  
|**Malzeme ortam**|Dolaylı aydınlatma öznitelikli geçerli piksel dağıtma renk katkı.<br /><br /> Bir piksel dağıtma rengini aydınlatma kaba yüzeyleriyle nasıl etkileşim kurduğu benzetimini yapar. Dolaylı aydınlatma nesneyi gerçek dünyadaki görünümünü nasıl katkıda yaklaşık için malzeme ortam parametresini kullanabilirsiniz.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float4`<br /> Dolaylı nedeniyle olan geçerli piksel dağıtma rengini — diğer bir deyişle, çevre — aydınlatma.|**Erişim**<br /> **Ortak** modeli Düzenleyicisi'nden ayarlayın; tersi durumda, özelliğini etkinleştirmek için **özel**.<br /><br /> **Değer**<br /> Dolaylı nedeniyle olan geçerli piksel dağıtma rengini — diğer bir deyişle, çevre — aydınlatma.|  
|**Malzeme dağıtma**|Geçerli piksel doğrudan aydınlatma nasıl diffuses açıklar rengi.<br /><br /> Bir piksel dağıtma rengini aydınlatma kaba yüzeyleriyle nasıl etkileşim kurduğu benzetimini yapar. Geçerli piksel doğrudan aydınlatma nasıl diffuses değiştirmek için malzeme Dağıt parametresini kullanabilirsiniz — diğer bir deyişle, yönlü, nokta ve nokta ışık.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float4`<br /> Geçerli piksel doğrudan aydınlatma nasıl diffuses açıklar rengi.|**Erişim**<br /> **Ortak** modeli Düzenleyicisi'nden ayarlayın; tersi durumda, özelliğini etkinleştirmek için **özel**.<br /><br /> **Değer**<br /> Geçerli piksel doğrudan aydınlatma nasıl diffuses açıklar rengi.|  
|**Malzeme Yayıcı**|Kendisi için sağladığı aydınlatma öznitelikli geçerli piksel renk katkı.<br /><br /> Işıyan nesne benzetimini yapmak için kullanabilirsiniz; diğer bir deyişle, kendi ışık sağlayan bir nesne. Bu açık diğer nesneleri etkilemez.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float4`<br /> Nedeniyle geçerli piksel renk katkı aydınlatma otomatik olarak sağlanır.|**Erişim**<br /> **Ortak** modeli Düzenleyicisi'nden ayarlayın; tersi durumda, özelliğini etkinleştirmek için **özel**.<br /><br /> **Değer**<br /> Nedeniyle geçerli piksel renk katkı aydınlatma otomatik olarak sağlanır.|  
|**Malzeme aynasal**|Geçerli piksel doğrudan aydınlatma nasıl yansıtır açıklar rengi.<br /><br /> Bir piksel aynasal rengi aydınlatma kesintisiz, yansıtma benzeri yüzeyleriyle nasıl etkileşim kurduğu benzetimini yapar. Geçerli piksel doğrudan aydınlatma nasıl yansıtır değiştirmek için malzeme aynasal parametresini kullanabilirsiniz — diğer bir deyişle, yönlü, nokta ve nokta ışık.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float4`<br /> Geçerli piksel doğrudan aydınlatma nasıl yansıtır açıklar rengi.|**Erişim**<br /> **Ortak** modeli Düzenleyicisi'nden ayarlayın; tersi durumda, özellik izin vermek için **özel**.<br /><br /> **Değer**<br /> Geçerli piksel doğrudan aydınlatma nasıl yansıtır açıklar rengi.|  
|**Malzeme aynasal güç**|Aynasal yoğunluğunu açıklayan bir skaler değere vurgular.<br /><br /> Aynasal vurgular hale büyük aynasal güç, daha güçlü ve beklediğinizden çok daha büyük.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float`<br /> Geçerli pikselini aynasal vurgular yoğunluğunu açıklar üstel bir terim.|**Erişim**<br /> **Ortak** modeli Düzenleyicisi'nden ayarlayın; tersi durumda, özelliğini etkinleştirmek için **özel**.<br /><br /> **Değer**<br /> Aynasal yoğunluğunu tanımlar üs geçerli pikselini vurgular.|  
|**Normalleştirilmiş zamanı**|Saniye cinsinden zaman normalleştirilmiş aralık [0, 1], 1, zaman zaman eriştiği gibi 0 olarak sıfırlar.<br /><br /> Bu gölgelendirici hesaplamaları, parametre olarak Örneğin, doku koordinatları, renk değerleri veya diğer öznitelikleri animasyon eklemek için kullanabilirsiniz.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float`<br /> Normalleştirilmiş saniye süre.|Yok.|  
|**Saat**|Saniye cinsinden süre.<br /><br /> Bu gölgelendirici hesaplamaları, parametre olarak Örneğin, doku koordinatları, renk değerleri veya diğer öznitelikleri animasyon eklemek için kullanabilirsiniz.<br /><br /> **Çıktı:**<br /><br /> `Output`: `float`<br /> Saniye cinsinden süre.|Yok.|