---
title: "length özelliği (işlev) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- length Property
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Length property
- length property (function)
ms.assetid: fdc8e1c9-0dac-4e1b-ba3a-11073c37ef63
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4fbd0334c18da2c6ef8de8366555d79f791e6855
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="length-property-function-javascript"></a>length Özelliği (İşlev) (JavaScript)
Bir işlev için tanımlanmış bağımsız değişken sayısı alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
functionName.length  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli *functionName* işlevi adıdır.  
  
 **Uzunluğu** özelliğinin bir işlevin başlatıldığı işlevin tanımında bağımsız değişken sayısı için komut dosyası altyapısı tarafından işlevi örneği oluşturulduğunda.  
  
 Bir işlev bağımsız değişkenleri değerinden farklı sayıda çağrıldığında neler kendi **uzunluğu** özelliği işlev bağlıdır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir **uzunluğu** özelliği:  
  
```JavaScript  
function ArgTest(a, b){  
    var s = "";  
  
    s += "Expected Arguments: " + ArgTest.length;  
    s += "<br />";  
    s += "Passed Arguments: " + arguments.length;  
  
    return s;  
}  
  
document.write(ArgTest(1, 2));  
  
// Output:   
// Expected Arguments: 2  
// Passed Arguments: 2  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [arguments özelliği (işlev)](../../javascript/reference/arguments-property-function-javascript.md)   
 [length özelliği (dizi)](../../javascript/reference/length-property-array-javascript.md)   
 [length özelliği (dize)](../../javascript/reference/length-property-string-javascript.md)