---
title: "Kodlanacak URI geçersiz karakter içeriyor | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.WebClient.Help.SCRIPT5024
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: a3f0fdbb-8d4b-41ae-a396-43dfc9483760
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1e93d145ea6b0991123c2a7c80f8acf54a83a264
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="the-uri-to-be-encoded-contains-an-invalid-character"></a>Kodlanacak URI geçersiz karakter içeriyor
Bir dizeyi bir URI (Tekdüzen Kaynak Tanımlayıcısı) olarak kodlanacak çalıştı, ancak geçersiz karakterler içeriyor. Çoğu karakter dizeleri için URI dönüştürülecek içinde geçerli olsa da, bazı Unicode karakter sıraları geçersiz.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Kodlanacak dize yalnızca geçerli Unicode sıraları içerir emin olun. Tam bir URI, bileşenleri ve ayırıcılar bir dizi oluşur. Köşeli adlarında bileşenleri temsil eder ve ":", "/", ";" ve "?" ayırıcı olarak kullanılan ayrılmış karakterler. Genel biçimi şöyledir:  
  
    ```JavaScript  
    <Scheme>:<first>/<second>;<third>?<fourth>  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [encodeURI işlevi](../../javascript/reference/encodeuri-function-javascript.md)   
 [Encodeurıcomponent işlevi](../../javascript/reference/encodeuricomponent-function-javascript.md)