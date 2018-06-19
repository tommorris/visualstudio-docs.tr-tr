---
title: VBArray bekleniyor | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5013
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f2998d7d-13a4-4bbe-b872-3ff3316551e4
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9b07c5e08e4178c9c31045317627424f5192f5e1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788795"
---
# <a name="vbarray-expected"></a>VBArray bekleniyor
Bir tane bekleniyordu yükleyen bir Visual Basic safeArray değil bir nesne sağlanan.  
  
```  
new VBArray(safeArray);  
```  
  
 VBArrays salt okunurdur ve doğrudan oluşturulamıyor. SafeArray bağımsız değişkeni bir VBArray değerdir ve VBArray değeri için iletilmeden önce almış `VBArray` Oluşturucusu. Bu, varolan bir ActiveX veya başka bir nesne değeri alarak yalnızca yapılabilir.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Yalnızca geçirdiğiniz olun **VBArray** nesneleri **VBArray** Oluşturucusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VBArray nesnesi](../../javascript/reference/vbarray-object-javascript.md)   
 [Dizileri kullanma](../../javascript/advanced/using-arrays-javascript.md)