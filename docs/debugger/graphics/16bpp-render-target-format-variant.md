---
title: "16bpp hedef biçimi değişken işleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24b22ad9-5ad0-4161-809a-9b518eb924bf
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1ed6ee80d2c12a135b2679ce115ef490c8c617da
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="16bpp-render-target-format-variant"></a>16bpp işleme hedef biçimi değişken
Piksel biçimlendirmek için DXGI_FORMAT_B5G6R5_UNORM tüm ayarlar hedefleri işlemek ve arabellek yedekleyin.  
  
## <a name="interpretation"></a>Yorumu  
 Genellikle bir işleme hedefi veya geri arabellek B8G8R8A8_UNORM gibi 32bpp (32 bit / piksel) biçimi kullanır. 32bpp biçimleri çok fazla bellek bant genişliği tüketebilir. B5G6R5_UNORM biçimi 32bpp biçimlerinin boyutunda 16bpp biçimde olduğundan kullanmadan baskısı bellek bant genişliği, ancak daha az renk uygunluğunu artması pahasına olur hafifletmek.  
  
 Bu değişken bir büyük performans kazancı gösteriyorsa, bu büyük olasılıkla uygulamanızı çok fazla bellek bant genişliği harcar gösterir. Profili çerçeve overdraw önemli miktarda yükselmesine veya çok Alfa karışım içerdiğinde performans artışı özellikle bildirilebilir.  
  
 Uygulamanız tarafından işlenen planda türlerini yüksek kaliteli renk çoğaltılması gerekmez, alfa kanal sağlamak için işleme hedefi gerektirmeyen ve kesintisiz gradyan genellikle içermeyen — azaltılmış renk altında yapıtları bant oluşturma için açık olan doğruluk — bellek bant genişliği kullanımını azaltmak için 16bpp işleme hedef biçimine kullanmayı düşünün.  
  
 Yüksek kaliteli renk çoğaltılması ya da bir alfa kanal uygulamanızda işlendiğini planda gerektiren veya kesintisiz gradyan ortak, bellek bant genişliği kullanımını azaltmak için diğer stratejileri düşünün — Örneğin, overdraw veya Alfa karışım miktarının azaltılması framebuffer boyutunu azaltma veya sıkıştırmayı etkinleştirme ya da kendi boyutlarını azaltarak daha az bellek bant genişliği için doku kaynakları değiştirme. Her zamanki gibi görüntü kalitesini herhangi bir bu en iyi duruma getirme ile gelen dengelemeler dikkate almanız gerekir.  
  
 Uygulamanızı bir 16bpp geri arabellek geçiş yararlanabileceğini ancak takas zincirinin parçasıdır DXGI_FORMAT_B5G6R5_UNORM kullanılarak oluşturulan takas zincirleri için desteklenen geri arabelleği biçim olmadığı için ek adımlar uygulamanızı varsa `D3D11CreateDeviceAndSwapChain` veya `IDXGIFactory::CreateSwapChain`. Bunun yerine, kullanarak B5G6R5_UNORM biçimi işleme hedefi oluşturmak zorunda `CreateTexture2D` ve bunun yerine işlemek için. Ardından, takas zinciri mevcut çağırmadan önce takas zinciri arka arabelleği üzerine işleme hedef kaynak doku olarak işleme hedefi ile tam ekran dört çizerek kopyalayın. Bu, bazı bellek bant genişliği tüketecektir fazladan bir adım olsa da, işleme işlemlerinin çoğu 16bpp işleme hedefi etkilediğinden daha az bant genişliği kullanır; Bu işleme hedefi için takas zinciri arka arabelleği kopyalayarak tüketilen daha fazla bant genişliği kaydederse, işleme performansı geliştirildi.  
  
 Döşeli işleme tekniklerini kullanın GPU mimarileri framebuffer daha büyük bir kısmını her döşemesinin yerel framebuffer önbelleğinde sığabilecek çünkü bir 16bpp framebuffer biçimi kullanarak önemli performans avantajı görebilirsiniz. Döşeli işleme mimariler, bazen mobil ahizeleri ve tablet bilgisayarlar GPU içinde bulunur; Bu özel dışında nadiren görünürler.  
  
## <a name="remarks"></a>Açıklamalar  
 İşleme hedef biçimine DXGI_FORMAT_B5G6R5_UNORM için her çağrıda sıfırlanır `ID3D11Device::CreateTexture2D` işleme hedefi oluşturur. Özellikle, bir işleme hedef pDesc içinde geçirilen D3D11_TEXTURE2D_DESC nesnesi açıklar olduğunda biçimi geçersiz kılınır; Yani:  
  
-   BindFlags üye D3D11_BIND_REDNER_TARGET bayrağı ayarlanmış sahiptir.  
  
-   BindFlags üye temizlenmiş D3D11_BIND_DEPTH_STENCIL bayrağı vardır.  
  
-   Kullanım üye D3D11_USAGE_DEFAULT için ayarlanır.  
  
## <a name="restrictions-and-limitations"></a>Kısıtlamalar ve sınırlamalar  
 Alfa içerik B5G6R5 biçimi alfa kanal sahip olmadığından, bu değişken tarafından korunmaz. Uygulamanızın işleme alfa kanalı oluşturma hedefiniz olarak gerektiriyorsa, yalnızca B5G6R5 biçimine geçemezsiniz.  
  
## <a name="example"></a>Örnek  
 **16bpp işleme hedef biçimi** değişken çoğaltılamaz kullanılarak oluşturulan işleme hedefler için `CreateTexture2D` aşağıdakine benzer bir kod kullanarak:  
  
```  
D3D11_TEXTURE2D_DESC target_description;  
  
target_description.BindFlags = D3D11_BIND_RENDER_TARGET;  
target_description.Format = DXGI_FORMAT_B5G6R5_UNORM;  
d3d_device->CreateTexture2D(&target_description, nullptr, &render_target);  
```