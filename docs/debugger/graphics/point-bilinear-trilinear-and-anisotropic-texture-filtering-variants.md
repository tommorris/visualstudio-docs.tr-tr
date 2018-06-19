---
title: Çeşitleri filtreleme noktası, çift doğrusal, Trilinear ve Eşyönsüz doku | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 57d14fc9-b5f7-45ee-9717-48086886742d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8002a0f85d2e2e04ff061c1f156b6c8528d85d07
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31474511"
---
# <a name="point-bilinear-trilinear-and-anisotropic-texture-filtering-variants"></a>Noktası, çift doğrusal, Trilinear ve Eşyönsüz doku çeşitleri filtreleme
Uygun doku örnekleyicileri üzerinde filtreleme modu geçersiz kılar.  
  
## <a name="interpretation"></a>Yorumu  
 Farklı performans maliyetleri ve görüntü kalitesini doku örnekleme farklı yöntemleri vardır. Maliyet artan sırada — ve görsel kalite artırma — filtre modu:  
  
1.  (Ucuz ve en kötü görsel kalite) filtreleme noktası  
  
2.  Çift doğrusal filtreleme  
  
3.  Trilinear filtreleme  
  
4.  Eşyönsüz (en pahalı, en iyi görsel kalite) filtreleme  
  
 Her değişken performans maliyetini önemli ya da daha fazla yoğunluklu filtreleme modlarıyla artırır ise, maliyeti daha yüksek görüntü kalitesini karşı tartmanız. Değerlendirmenize göre bağlı olarak, visual kalitesini artırmak için ek performans maliyetleri kabul edebilir ya da daha yüksek bir kare hızı elde etmek için veya diğer yollarla kullanabilirsiniz performans geri kazanmak için görsel kalite azaltılabilir kabul edebilir.  
  
 Performans maliyeti düşünülerek veya filtreleme modu bağımsız olarak sürekli olduğunu fark ederseniz — Örneğin, hedefleme GPU olduğunda bol miktarda gölgelendirici işleme ve bellek bant genişliği — en iyi resmi elde etmek için Eşyönsüz filtreleme kullanmayı düşünün uygulamanızda kalitesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu çeşitleri çağrıları örneği durumlarına geçersiz kılma `ID3D11DeviceContext::PSSetSamplers` uygulama tarafından sağlanan örneği'nın filtre modu bunlardan birini olduğu:  
  
-   `D3D11_FILTER_MIN_MAG_MIP_POINT`  
  
-   `D3D11_FILTER_MIN_MAG_POINT_MIP_LINEAR`  
  
-   `D3D11_FILTER_MIN_POINT_MAG_LINEAR_MIP_POINT`  
  
-   `D3D11_FILTER_MIN_POINT_MAG_MIP_LINEAR`  
  
-   `D3D11_FILTER_MIN_LINEAR_MAG_MIP_POINT`  
  
-   `D3D11_FILTER_MIN_LINEAR_MAG_POINT_MIP_LINEAR`  
  
-   `D3D11_FILTER_MIN_MAG_LINEAR_MIP_POINT`  
  
-   `D3D11_FILTER_MIN_MAG_MIP_LINEAR`  
  
-   `D3D11_FILTER_ANISOTROPIC`  
  
 İçinde **doku noktası filtreleme** değişken, uygulama tarafından sağlanan filtre modu değiştirilir `D3D11_FILTER_MIN_MAG_MIP_POINT`; **çift doğrusal doku filtreleme** onu ile değiştirilir variant `D3D11_FILTER_MIN_MAG_LINEAR_MIP_POINT`; ve **Trilinear doku filtreleme** onu ile değiştirilir variant `D3D11_FILTER_MIN_MAG_MIP_LINEAR`.  
  
 İçinde **Eşyönsüz doku filtreleme** değişken, uygulama tarafından sağlanan filtre modu değiştirilir `D3D11_FILTER_ANISOTROPIC`, ve maksimum Anisotropy 16 olarak ayarlanır.  
  
## <a name="restrictions-and-limitations"></a>Kısıtlamalar ve sınırlamalar  
 Direct3D içinde özellik düzeyini 9.1 2 x maksimum anisotropy belirtir. Çünkü **Eşyönsüz doku filtreleme** değişken çalışır 16 x anisotropy özel olarak kullanmak, çerçeve analizi bir özellik düzeyinde 9.1 cihazda çalıştırıldığında kayıttan yürütme başarısız olur. Bu sınırlama tarafından etkilenen Çağdaş cihazlar ARM tabanlı Surface RT ve yüzeyini 2 Windows tabletler içerir. Hala bazı durumlarda bilgisayarları da etkilenebilir, ancak yaygın olarak kullanılmayan olarak kabul ve giderek seyrek bulunabilir eski GPU.  
  
## <a name="example"></a>Örnek  
 **Doku noktası filtreleme** değişken bu kodu kullanarak yeniden ürettiniz:  
  
```  
D3D11_SAMPLER_DESC sampler_description;  
  
// ... other sampler description setup ...  
  
sampler_description.Filter = D3D11_FILTER_MIN_MAG_MIP_POINT;  
  
d3d_device->CreateSamplerState(&sampler_desc, &sampler);  
d3d_context->PSSetSamplers(0, 1, &sampler  
```  
  
## <a name="example"></a>Örnek  
 **Çift doğrusal doku filtreleme** değişken bu kodu kullanarak yeniden ürettiniz:  
  
```  
D3D11_SAMPLER_DESC sampler_description;   
  
// ... other sampler description setup ...  
  
sampler_description.Filter = D3D11_FILTER_MIN_MAG_LINEAR_MIP_POINT;  
  
d3d_device->CreateSamplerState(&sampler_desc, &sampler);  
d3d_context->PSSetSamplers(0, 1, &sampler  
```  
  
## <a name="example"></a>Örnek  
 **Trilinear doku filtreleme** değişken bu kodu kullanarak yeniden ürettiniz:  
  
```  
D3D11_SAMPLER_DESC sampler_description;   
  
// ... other sampler description setup ...  
  
sampler_description.Filter = D3D11_FILTER_MIN_MAG_MIP_LINEAR;  
  
d3d_device->CreateSamplerState(&sampler_desc, &sampler);  
d3d_context->PSSetSamplers(0, 1, &sampler  
```  
  
## <a name="example"></a>Örnek  
 **Eşyönsüz doku filtreleme** değişken bu kodu kullanarak yeniden ürettiniz:  
  
```  
D3D11_SAMPLER_DESC sampler_description;   
  
// ... other sampler description setup ...  
  
sampler_description.Filter = D3D11_FILTER_ANISOTROPIC;  
sampler_description.MaxAnisotropy = 16;  
  
d3d_device->CreateSamplerState(&sampler_desc, &sampler);  
d3d_context->PSSetSamplers(0, 1, &sampler  
```