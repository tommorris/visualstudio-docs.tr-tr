---
title: Dizi uzunluğu sonlu pozitif bir sayı atanmalıdır | Microsoft Docs
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
- VS.WebClient.Help.SCRIPT5030
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: c51c66a4-a543-4e95-b18d-2cfbcb3d1fdd
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 63a9d714173334192028b9096de41968befa85ef
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788885"
---
# <a name="array-length-must-be-assigned-a-finite-positive-number"></a>Dizi uzunluğuna sonsuz olmayan pozitif bir sayı atanmalıdır
Ayarlarken **uzunluğu** varolan özelliği **dizi** nesnesi, pozitif bir sayı veya sıfır olmayan bir dizi uzunluğu belirtilmiş. Bir değere atadığınızda, bu hata oluşur. **uzunluğu** özelliği bir `Array` negatif nesne veya sayı olmayan (`NaN`). Unutmayın [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] kesirli sayılar tüm tamsayılara otomatik olarak dönüştürür.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Length özelliği pozitif bir tamsayı atayın. En büyük tamsayı değeri (yaklaşık 4 milyar) dışında bir dizi boyutu üst sınırı yoktur. Doğru bir şekilde ayarlamak için aşağıdaki örnekte gösterilmiştir **uzunluğu** özelliği bir **dizi** nesnesi.  
  
    ```JavaScript  
    var my_array = new Array();  
    my_array.length = 99;  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizileri kullanma](../../javascript/advanced/using-arrays-javascript.md)