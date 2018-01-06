---
title: "0 x-2 x-4 x MSAA çeşitleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 668a6603-5082-4c78-98e6-f3dc871aa55b
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 77e4d199fe0c0ae1d876eae62014e6aaabd6f643
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="0x2x4x-msaa-variants"></a>0 x / 2 x / 4 x MSAA çeşitleri
Geçersiz kılmaları birden çok örnek yumuşatma (MSAA) ayarları tüm hedefleri işlemek ve zincirleri değiştirme.  
  
## <a name="interpretation"></a>Yorumu  
 Birden çok örnek düzgünleştirme her piksel birden fazla konumda adresindeki örnekleri gerçekleştirerek görsel kalite artırır; Daha fazla örnekleri MSAA daha üst düzey almak ve MSAA, yalnızca bir örnek piksel Merkezi'nden alınır. MSAA uygulamanızda genellikle başlandığında uygun belirgin ancak işleme performans, ancak belirli iş yükleri altındaki veya belirli GPU maliyeti, neredeyse hiçbir etkisi ile önceki.  
  
 Uygulamanızı etkin MSAA zaten varsa, daha az MSAA çeşitleri varolan, üst düzey MSAA doğurur göreli performans maliyeti gösterir. Özellikle, 0 x MSAA değişken uygulamanızı MSAA olmadan performanslarını gösterir.  
  
 Uygulamanızı etkin MSAA zaten yoksa 2 x MSAA ve 4 x MSAA çeşitleri uygulamanızda etkinleştirme göreli performans maliyetini gösterir. Maliyet çalışarak düşük olduğunda, uygulamanızın görüntü kalitesini geliştirmek MSAA etkinleştirmeyi düşünün.  
  
> [!NOTE]
>  Donanımınız için tüm biçimleri MSAA tam olarak desteklemeyebilir. Bu çeşitleri hiçbirini geçici çalışılan olamaz bir donanım sınırlama karşılaşırsanız, kendi performansını Özet Tablo sütununda boştur ve bir hata iletisi oluşturulur.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu çeşitleri örnek sayısı ve örnek kaliteli bağımsız değişkenler çağrıları üzerinde geçersiz kılma `ID3DDevice::CreateTexture2D` işleme hedefleri oluşturun. Özellikle, bu parametreler geçersiz kılınır zaman:  
  
-   `D3D11_TEXTURE2D_DESC` Nesnesi geçirildi `pDesc` bir işleme hedef; açıklar:  
  
    -   BindFlags üye D3D11_BIND_TARGET bayrağı ya da D3D11_BIND_DEPTH_STENCIL bayrağı ayarlanmış sahiptir.  
  
    -   Kullanım üye D3D11_USAGE_DEFAULT için ayarlanır.  
  
    -   CPUAccessFlags üye 0 olarak ayarlanır.  
  
    -   MipLevels üye 1 olarak ayarlayın.  
  
-   İstenen işleme tarafından belirlendiği şekilde hedef biçimi (D3D11_TEXTURE2D_DESC::Format üye) için istenen örnek sayısı (0, 2 veya 4) ve örnek kalite (0) cihaz destekler `ID3D11Device::CheckMultisampleQualityLevels`.  
  
 D3D11_TEXTURE2D_DESC::BindFlags üye ayarlanmış D3D_BIND_SHADER_RESOUCE veya D3D11_BIND_UNORDERED_ACCESS bayrağı varsa, doku iki sürümü oluşturulur; ilk işleme hedefi olarak kullanmak üzere işaretli Bu bayraklar vardır ve diğer ilk sürüm için resolve arabellek olarak davranmak üzere dokunulmadan Bu bayraklar sahip olmayan MSAA doku olur. Gölgelendirici kaynak olarak ya da düzenlenmemiş erişim MSAA doku kullanarak geçerli olması olası gerekli olmasıdır — MSAA olmayan doku beklediğiniz çünkü Örneğin, üzerinde hareket gölgelendirici hatalı sonuçlar üretir. Daha sonra değişken MSAA olmayan ikincil doku oluşturduysa, MSAA işleme hedef aygıt bağlamından unset olduğunda içeriği MSAA olmayan doku çözümlenir. Benzer şekilde, MSAA işlemek her hedef gölgelendirici kaynak olarak bağlanmalıdır veya düzenlenmemiş erişim görünümünde kullanılır, çözümlenen MSAA olmayan doku yerine bağlıdır.  
  
 Bu çeşitleri ayrıca kullanılarak oluşturulan tüm takas zincirleri MSAA ayarlarını geçersiz kılmanız `IDXGIFactory::CreateSwapChain`, `IDXGIFactory2::CreateSwapChainForHwnd`, `IDXGIFactory2::CreateSwapChainForCoreWindow`, `IDXGIFactory2::CreateSwapChainForComposition`, ve `ID3D11CreateDeviceAndSwapChain`.  
  
 Net bu değişikliklerin tüm işleme bir MSAA işleme hedefine yapılır ancak uygulamanızın bunlardan birini kullanıp kullanmadığını işlemek hedefler ya da değiştirme zinciri arabellekleri gölgelendirici kaynak görünümü veya düzenlenmemiş erişim görünümü olarak ve ardından veri örneklenen etkisidir çözümlenmiş gelen , işleme hedef MSAA olmayan kopyası.  
  
## <a name="restrictions-and-limitations"></a>Kısıtlamalar ve sınırlamalar  
 Direct3D11 içinde MSAA dokuları MSAA olmayan dokuları daha büyük/küçük harf kısıtlanır. Örneğin, çağıramazsınız `ID3D11DeviceContext::UpdateSubresource` bir MSAA doku ve arama `ID3D11DeviceContext::CopySubresourceRegion` örnek sayısı ve örnek kalitesi kaynak kaynak ve hedef kaynak, bu değişken bir MSAA ayarları geçersiz kılar kurduğunuzda gerçekleşebilir eşleşmiyorsa başarısız Kaynak, ancak diğer.  
  
 Kayıttan yürütme çakışmaları bu tür algıladığında, amaçlanan bir davranış çoğaltmak için en iyi çaba kolaylaştırır, ancak sonuçlarını tam olarak eşleştiğinden mümkün olmayabilir. Bunun etkilerini görünen şekilde bu çeşitleri performansını etkileyen seyrek olsa da, olası — Örneğin, ne zaman piksel gölgelendirici akış denetimi belirlenir bir doku tarafından kesin içerik — çünkü çoğaltılmış doku aynı içeriğe sahip olmayabilir.  
  
## <a name="example"></a>Örnek  
 Bu çeşitleri kullanılarak oluşturulan işleme hedefler için çoğaltılamaz `ID3D11Device::CreateTexture2D` aşağıdakine benzer bir kod kullanarak:  
  
```  
D3D11_TEXTURE2D_DESC target_description;  
target_description.BindFlags = D3D11_BIND_RENDER_TARGET;  
target_description.SampleDesc.Count = 4; // 4x MSAA, can be 2 or 0 instead  
target_description.SampleDesc.Quality = 0;  
d3d_device->CreateTexture2D(&target_description, nullptr, &render_target);  
```  
  
## <a name="example"></a>Örnek  
 Veya IDXGISwapChain::CreateSwapChain veya D3D11CreateDeviceAndSwapChain aşağıdakine benzer bir kod kullanarak kullanılarak oluşturulan takas zincirleri için:  
  
```  
DXGI_SWAP_CHAIN_DESC chain_description;  
chain_description.SampleDesc.Count = 4; // 4x MSAA, can be 2 or 0 instead  
chain_description.SampleDesc.Quality = 0;  
  
// Call IDXGISwapChain::CreateSwapChain or D3D11CreateDeviceAndSwapChain, etc.  
```