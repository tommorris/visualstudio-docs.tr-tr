---
title: BC doku sıkıştırma değişken | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 2d0f5305-585b-4b01-bc9a-7a32d6e991da
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 49dfc92eeede177e843c9fd98b16b030f76079c0
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="bc-texture-compression-variant"></a>BC doku sıkıştırma değişken
Bir B8G8R8X8, B8G8R8A8 veya R8G8B8A8 çeşididir piksel biçimine sahip dokular üzerinde sıkıştırmayı etkinleştirir engelleyin.  
  
## <a name="interpretation"></a>Yorumu  
 Blok tabanlı sıkıştırma biçimleri BC1, BC2, ister ve BC3 görüntü biçimlerini sıkıştırılmamış ve bu nedenle önemli ölçüde daha az bellek bant genişliği daha önemli ölçüde daha az bellek kaplar. 32 bit / piksel kullanan sıkıştırılmamış biçime ile karşılaştırıldığında, 8:1 sıkıştırma (önceki adıyla DXT1 da bilinir) BC1 erişir ve 4:1 (önceki adıyla DXT5 da bilinir) BC3 erişir. BC1 BC3 arasındaki fark BC3 blok sıkıştırılmış alfa kanal desteklerken BC1 bir alfa kanal desteklemiyor ' dir. Yüksek sıkıştırma oranları ikincil azalma tipik dokuları için görüntü kalitesini yoktur. Ancak, doku belirli türdeki sıkıştırılması engellemek — Örneğin, önemli olan küçük bir alanı değişim renk — kabul edilemez sonuçları olabilir.  
  
 Doku blok tabanlı sıkıştırma için uygundur ve renk uygunluğunu mükemmel yoktur, bellek kullanımını azaltmak ve daha az bant genişliği için bir blok sıkıştırılmış biçimi kullanmayı düşünün.  
  
## <a name="remarks"></a>Açıklamalar  
 Her çağrıda bir blok tabanlı sıkıştırma biçimi kullanarak dokuları Sıkıştır `ID3DDevice::CreateTexture2D` kaynağı doku oluşturur. Özellikle, doku sıkıştırılmış zaman:  
  
-   `D3D11_TEXTURE2D_DESC` Nesnesi geçirildi `pDesc` olan değişmeyen bir gölgelendirici kaynak; açıklar:  
  
    -   BindFlags üye yalnızca D3D11_BIND_SHADER_RESOURCE bayrağı ayarlanmış sahiptir.  
  
    -   Kullanım üye D3D11_USAGE_DEFAULT veya D3D11_USAGE_IMMUTABLE için ayarlanır.  
  
    -   CPUAccessFlags üye 0 (CPU erişimi yok) olarak ayarlayın.  
  
    -   SamplerDesc üyesi (hiçbir çok örnekli yumuşatma (MSAA)) 1'e ayarlayın, sayım üyesi vardır.  
  
-   İlk veri çağrısına sağlanan `CreateTexture2D`.  
  
 Desteklenen kaynak biçimlerini ve bunların blok sıkıştırılmış biçimlerini aşağıda verilmiştir.  
  
|Özgün biçiminde (Başlangıç)|Sıkıştırılmış biçimi (Bitiş)|  
|------------------------------|------------------------------|  
|`DXGI_FORMAT_B8G8R8X8_UNORM`|BC1 (önceki adıyla DXT1)|  
|`DXGI_FORMAT_B8G8R8X8_UNORM_SRGB`|BC1|  
|`DXGI_FORMAT_B8G8R8X8_TYPELESS`|BC1|  
|`DXGI_FORMAT_B8G8R8A8_UNORM`|BC3 (önceki adıyla DXT5)|  
|`DXGI_FORMAT_B8G8R8A8_UNORM_SRGB`|BC3|  
|`DXGI_FORMAT_B8G8R8A8_TYPELESS`|BC3|  
|`DXGI_FORMAT_R8G8B8A8_UNORM`|BC3|  
|`DXGI_FORMAT_R8G8B8A8_UNORM_SRGB`|BC3|  
|`DXGI_FORMAT_R8G8B8A8_TYPELESS`|BC3|  
  
 Listede olmayan bir biçimde, doku varsa, doku değiştirilmez.  
  
## <a name="restrictions-and-limitations"></a>Kısıtlamalar ve sınırlamalar  
 Bazen B8G8R8A8 veya R8G8B8A8 resim biçimleri varyasyonuyla oluşturulan dokuları alfa kanal gerçekte kullanmadığınız ancak veya kullanılan olup olmadığını öğrenmek değişken bir yolu yoktur. Alfa kanal kullanılan durumda doğruluk korumak için değişken her zaman daha az verimli BC3 biçimine Bu biçimler kodlar. Grafik Çerçeve Çözümlemesi değişken daha etkili BC1 biçimi kullanabilmesi için alfa kanal kullanmadığınızda bir değişim B8G8R8X8 resim biçimi kullanarak uygulamanızın olası işleme performansını Bu değişken ile daha iyi anlamanıza yardımcı olabilir.  
  
## <a name="example"></a>Örnek  
 Bu değişken blok-dokuları çağırmadan önce çalışma zamanında sıkıştırır `CreateTexture2D`. Üretim kodu için bu yaklaşım karşı daha fazla disk alanı sıkıştırılmamış dokuları tükettiği için ve blok tabanlı sıkıştırma önemli gerektirdiğinden ek adım uygulamanız yükleme sürelerini önemli ölçüde artırabildiğinden öneririz kodlanacak hesaplama kaynakları. Bunun yerine, bir görüntü Düzenleyicisi veya yapı hattınızı parçası olan görüntü işlemci kullanarak, doku çevrimdışı Sıkıştır öneririz. Bu yaklaşım disk alanı gereksinimlerini azaltmak, çalışma zamanında uygulamanızda ek yükü ortadan kaldırmak ve en iyi görüntü kalitesini kullanabilmesi için daha fazla işleme süresi göze.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yarı/Çeyrek doku boyutları değişken](half-quarter-texture-dimensions-variant.md)