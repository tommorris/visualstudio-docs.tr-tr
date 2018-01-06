---
title: "Altı aylık doku değişken boyutları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 282e9bbb-51aa-4cd0-8e5c-0901268c29e5
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 93431c8863e2b30fb98d00bec5112257e54496f1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="halfquarter-texture-dimensions-variant"></a>Yarı/Çeyrek doku boyutları değişken
Hedefleri işlenmeyebilir dokuları doku boyutlarında azaltır.  
  
## <a name="interpretation"></a>Yorumu  
 Daha küçük dokuları daha az bellek kaplar ve bu nedenle daha az bellek bant genişliği ve GPU'ın doku önbellek Basıncı azaltabilirsiniz. Ancak, özellikle bunlar yakından 3B Sahne görüntülenebilir veya büyütme altında görüntülenen küçük kendi ayrıntı azaltılmış görüntü kalitesini neden olabilir.  
  
 Bu değişken bir büyük performans kazancı gösteriyorsa, uygulamanızı çok fazla bellek bant genişliği, doku önbelleğe inefficiently kullanır veya her ikisini tüketir belirtebilirsiniz. Ayrıca, doku, bulunandan daha fazla GPU belleği sistem belleği disk belleğine alınacak dokuları neden olan kaplar olduğunu gösterebilir.  
  
 Uygulamanız çok fazla bellek bant genişliği harcar veya doku önbellek inefficiently kullanıyorsa, doku, ancak yalnızca uygun dokuları için MIP eşlemeleri etkinleştirmeyi düşünün sonra boyutunu azaltmayı deneyin. Daha küçük dokular gibi MIP Eşlenen dokuları daha az bellek bant genişliği tüketebilir — daha fazla GPU belleği kaplar rağmen — ve artış önbellek kullanımı, ancak doku ayrıntı azaltmak yok. Daha fazla bellek kullanımı için sistem belleği disk belleğine alınacak dokuları neden olmaz her MIP eşlemeleri öneririz.  
  
 Bulunandan daha fazla GPU belleği, doku kaplar, dokuları, ancak yalnızca uygun dokuları sıkıştırma düşündüğünüz sonra boyutunu azaltmayı deneyin. Daha küçük dokular gibi sıkıştırılmış dokuları daha az bellek kaplar ve sistem bellek sayfasına gereksinimini azaltır, ancak kendi renk güvenilirlik azalır. Sıkıştırma içeriklerine bağlı olarak tüm dokuları için uygun değildir — Örneğin, önemli olan küçük bir alanı değişim renk — ancak birçok dokuları için kendi boyutunun azaltılması daha iyi genel görüntü kalitesini sıkıştırma koruyabilirsiniz.  
  
## <a name="remarks"></a>Açıklamalar  
 Doku boyutları her çağrıda azaltılmış `ID3D11Device::CreateTexture2D` kaynağı doku oluşturur. Doku boyutları D3D11_TEXTURE2D_DESC nesne içinde geçirildiğinde özellikle azaltılır `pDesc` işlemede kullanılan; olan bir doku açıklar:  
  
-   BindFlags üye yalnızca D3D11_BIND_SHADER_RESOURCE bayrağı ayarlanmış sahiptir.  
  
-   D3D11_RESOURCE_MISC_TILE_POOL bayrağı veya (döşeli kaynakları değil yeniden boyutlandırılıyor) D3D11_RESOURCE_MISC_TILED bayrağı ayarlanmış MiscFlags üye yok.  
  
-   Doku biçimi işleme hedef olarak desteklenen — D3D11_FORMAT_SUPPORT_RENDER_TARGET tarafından belirlendiği şekilde — doku boyutunu azaltmak için gerekli olduğu. Bunlar hedefleri oluşturma gibi desteklenmeyen olsa bile BC1, BC2 ve BC3 biçimlerinin de desteklenir.  
  
 İlk veri uygulama tarafından sağlanırsa, doku oluşturmadan önce bu değişken doku veri uygun boyuta ölçeklendirir. İlk veri bloğu sıkıştırılmış biçimde BC1, BC2 veya BC3 gibi sağlanırsa, kodunu çözdü, ölçeklendirilebilir ve daha küçük doku oluşturmak için kullanılmadan önce yeniden kodlanmış. (Blok tabanlı sıkıştırma yapısını ek kod çözme-ölçek-kodlama işlemi neredeyse her zaman bir blok sıkıştırılmış doku daha önce kodlanmamış doku ölçeklendirilmiş bir sürümünden oluşturulduğunda daha düşük görüntü kalitesini neden anlamına gelir.)  
  
 MIP eşlemeleri için doku etkinleştirilirse, değişken MIP düzey sayısını uygun şekilde azaltır — üç aylık dönem boyutuna ölçekleme sırasında bir yarı boyutlu ölçekleme sırasında daha az veya iki az.  
  
## <a name="example"></a>Örnek  
 Bu değişken dokuları çağırmadan önce çalışma zamanında yeniden boyutlandırır `CreateTexture2D`. Üretim kodu için bu yaklaşım karşı daha fazla disk alanı tam boyutlu dokular tükettiği için ve ek bir adım yükleme süreleri uygulamanızda artırabildiğinden öneririz; özellikle sıkıştırılmış dokuları gerektiren önemli hesaplama kodlanacak kaynakları. Bunun yerine, bir görüntü Düzenleyicisi veya yapı hattınızı parçası olan görüntü işlemci kullanarak çevrimdışı, dokuları yeniden boyutlandırır öneririz. Bu yaklaşım disk alanı gereksinimlerini azaltmak ve uygulamanızda çalışma zamanı ek yükü ortadan kaldırmak ve en iyi görüntü kalitesini küçültme veya, doku sıkıştırma kullanabilmesi için daha fazla işleme süresi göze.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MIP eşleme oluşturma değişken](mip-map-generation-variant.md)   
 [BC Doku Sıkıştırma Çeşidi](bc-texture-compression-variant.md)