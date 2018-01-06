---
title: "1 x 1 Görünüm penceresi boyutu değişken | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3dbc3247-00f5-4644-8ff9-72e9febcf09a
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ab9f8be1d202f21147afaf9f4f52a3c90c403ed8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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