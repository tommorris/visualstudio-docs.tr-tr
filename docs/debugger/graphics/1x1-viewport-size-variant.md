---
title: 1 x 1 Görünüm penceresi boyutu değişken | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 3dbc3247-00f5-4644-8ff9-72e9febcf09a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3f645c078314522d767e578cc6d5770969971c5f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="1x1-viewport-size-variant"></a>1 x 1 Görünüm penceresi boyutu değişken
Tüm işleme hedefleri görünüm penceresinin boyutlarında 1 x 1 piksel azaltır.  
  
## <a name="interpretation"></a>Yorumu  
 Daha küçük bir görünüm penceresinin gölgeli olmalı, ancak işlenmesi gereken köşeleri sayısını azaltmaz piksel sayısını azaltır. Görünüm penceresinin boyutları 1 x 1 piksel için etkili bir şekilde ayarlama piksel-uygulamanızı gölgelendirmesini ortadan kaldırır.  
  
 Bu değişken bir büyük performans kazancı gösteriyorsa, uygulamanızı çok fazla fillrate tüketir gösterebilir. Bu seçtiniz çözümleme hedef platformu için çok yüksek olduğunu veya uygulamanızı daha sonra üzerine önemli zaman gölgelendirme piksel harcadığı gösterebilir (overdraw). Bu sonuç öneren, framebuffer boyutunu azaltma veya overdraw miktarının azaltılması, uygulamanızın performansı iyileştirir.  
  
## <a name="remarks"></a>Açıklamalar  
 Görünüm penceresinin boyutları 1 x 1 piksel her çağrı için sonra sıfırlanır `ID3D11DeviceContext::OMSetRenderTargets` veya `ID3D11DeviceContext::RSSetViewports`.  
  
## <a name="example"></a>Örnek  
 Bu değişken, aşağıdakine benzer bir kod kullanarak çoğaltılamaz:  
  
```  
D3D11_VIEWPORT viewport;  
viewport.TopLeftX = 0;  
viewport.TopLeftY = 0;  
viewport.Width = 1;  
viewport.Height = 1;  
d3d_context->RSSetViewports(1, &viewport);  
```