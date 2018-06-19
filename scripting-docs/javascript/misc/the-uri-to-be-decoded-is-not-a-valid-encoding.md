---
title: Kodu çözülecek URI geçerli bir kodlamada değil | Microsoft Docs
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
- VS.WebClient.Help.SCRIPT5025
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 029e0790-ffd1-496d-8700-3b3dbac1b6fd
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2d37ca55dfd701aaeba2af729511a5ae6a4fa5f4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788843"
---
# <a name="the-uri-to-be-decoded-is-not-a-valid-encoding"></a>Kodu çözülecek URI geçerli bir kodlamada değil
Hatalı biçimlendirilmiş bir URI (Tekdüzen Kaynak Tanımlayıcısı) kod çözme girişiminde bulunuldu. URI'ler özel bir sözdizimi vardır; bir URI kullanılmadan önce çoğu alfasayısal olmayan karakter kodlanmış olması gerekir. Kullanabileceğiniz `encodeURI` ve `encodeURIComponent` bir normal bir URI oluşturmak için yöntem [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] dize.  
  
 Tam bir URI, bileşenleri ve ayırıcılar bir dizi oluşur. Genel biçimi şöyledir:  
  
```JavaScript  
<Scheme>:<first>/<second>;<third>?<fourth>  
```  
  
 Köşeli adlarında bileşenleri temsil eder ve ":", "/", ";" ve "?" ayırıcı olarak kullanılan ayrılmış karakterler.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Yalnızca geçerli URI'ler çözmeye çalıştığınız emin olun. Normal çözülemiyor [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] dizeleri gibi geçersiz karakterler içeriyor olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [decodeURI işlevi](../../javascript/reference/decodeuri-function-javascript.md)   
 [Decodeurıcomponent işlevi](../../javascript/reference/decodeuricomponent-function-javascript.md)