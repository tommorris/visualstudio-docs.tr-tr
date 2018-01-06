---
title: "MIP eşleme oluşturma değişken | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b4b3583-0b01-4f5d-aacb-3f96d19111d9
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f6b7773562ed7b09ca00f7fc471b7ee2924c0181
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="mip-map-generation-variant"></a>MIP eşleme oluşturma değişken
Hedefleri işlenmeyebilir dokuları MIP-eşlemeleri sağlar.  
  
## <a name="interpretation"></a>Yorumu  
 MIP eşlemeleri öncelikle küçültme altında dokuları yumuşatma yapıları ortadan kaldırmak için doku önceden hesaplama küçük sürümleri tarafından kullanılır. Bu ek dokuları GPU belleği kullanmasına rağmen — yaklaşık yüzde 33 özgün doku'den fazla — bunlar da GPU doku önbelleğinde daha kendi yüzey alanını en uygun ve içeriğinin daha yüksek kullanımı sağlamak için daha etkili.  
  
 3B görünümleri için bellek işleme performans ve görüntü kalitesini artırmak için ek dokular depolamak üzere kullanılabilir olduğunda MIP eşlemeleri öneririz.  
  
 Bu değişken bir önemli performans kazancı gösteriyorsa, MIP eşlemeleri etkinleştirme ve çoğu doku önbelleğinden alamıyorsanız böylece olmadan dokuları kullandığınızı gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Her çağrıda MIP eşleme oluşturma zorunlu `ID3D11Device::CreateTexture2D` kaynağı doku oluşturur. D3D11_TEXTUR2D_DESC nesne içinde geçirildiğinde MIP eşleme oluşturma özellikle zorlanır `pDesc` olan değişmeyen bir gölgelendirici kaynak; açıklar:  
  
-   BindFlags üye yalnızca D3D11_BIND_SHADER_RESOURCE bayrağı ayarlanmış sahiptir.  
  
-   Kullanım üye D3D11_USAGE_DEFUALT veya D3D11_USAGE_IMMUTABLE için ayarlanır.  
  
-   CPUAccessFlags üye 0 (CPU erişimi yok) olarak ayarlayın.  
  
-   SampleDesc üyesi (hiçbir çok örnekli yumuşatma (MSAA)) 1'e ayarlayın, sayım üyesi vardır.  
  
-   MipLevels üye 1 (varolan MIP-eşleme yok) olarak ayarlayın.  
  
 İlk veri uygulama tarafından sağlandığında doku biçimini otomatik MIP eşleme oluşturma desteklemesi gerekir — D3D11_FORMAT_SUPPORT_MIP_AUTOGEN tarafından belirlendiği şekilde — biçimi BC1, BC2 veya BC3; olmadıkça Aksi durumda doku değiştirilemez ve ilk veri sağlandığında MIP eşlemeleri üretilir.  
  
 İçin bir doku, MIP eşlemeleri otomatik olarak oluşturulan, çağrılar `ID3D11Device::CreateShaderResourceView` MIP zinciri doku Örnekleme sırasında kullanılacak kayıttan yürütme sırasında değiştirilmiş.  
  
## <a name="example"></a>Örnek  
 **MIP eşleme oluşturma** değişken bu kodu kullanarak yeniden ürettiniz:  
  
```  
D3D11_TEXTURE2D_DESC texture_description;  
  
// ...  
  
texture_description.MipLevels = 0; // generate a full mipchain  
  
std::vector<D3D11_SUBRESOURCE_DATA> initial_data(num_mips);  
  
for (auto&& mip_level : initial_data)  
{  
    // fill mip_level with the application-supplied initial data  
}  
  
d3d_device->CreateTexture2D(&texture_description, initial_data.data(), &texture)  
```  
  
 Bir tam MIP zinciri var. bir doku oluşturmak için `D3D11_TEXTURE2D_DESC::MipLevels` 0. Bir tam MIP zincirindeki MIP düzeyleri sayısıdır floor(log2(n) + 1), burada n, doku en büyük boyutu.  
  
 İlk veri sağladığınızda unutmayın `CreateTexture2D`, her MIP düzeyi için bir D3D11_SUBRESOURCE_DATA nesnesi sağlamanız gerekir.  
  
> [!NOTE]
>  Kendi MIP otomatik olarak üretmek yerine düzeyi içeriği sağlamak istiyorsanız, doku bir görüntüsünü kullanarak MIP Eşlenen dokuları destekleyen Düzenleyicisi'ni ve ardından dosyayı yüklemek oluşturup gerekir MIP düzeylere geçirmek `CreateTexture2D`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yarı/Çeyrek doku boyutları değişken](half-quarter-texture-dimensions-variant.md)