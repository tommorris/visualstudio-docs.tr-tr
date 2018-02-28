---
title: "Dizi uzunluğu sonlu pozitif bir tamsayı olması gerekir | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5029
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1a467040-4702-4178-848f-418a5974e907
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c6589bd2e9bb4acbec5f169087a49e64417dfae7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="array-length-must-be-a-finite-positive-integer"></a>Dizi uzunluğu sonlu pozitif bir tamsayı olmalıdır
Aradığınız **dizi** (tam sayılar oluşur sıfır artı pozitif tamsayılar kümesi) bir tam sayı olmayan bir bağımsız değişken Oluşturucu.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Pozitif tamsayılar yalnızca yeni bir oluştururken kullandığınız `Array` nesnesi. Bir tamsayı değil tek bir öğesi ile bir dizi oluşturmak istiyorsanız, bunu iki adımlı bir işlem. Önce bir dizi sahip bir öğe oluşturun, sonra değeri ilk öğe (array[0]). yerleştirin Bu hatayı oluşturan bir örnek verilmiştir.  
  
    ```JavaScript  
    var piArray = new Array(3.14159);  
    ```  
  
     Aşağıdaki örnek, bir dizi olan tek bir sayısal öğesi belirtmek için doğru bir şekilde gösterir.  
  
    ```JavaScript  
    var piArray = new Array(1);  
    piArray [0] = 3.14159;  
    ```  
  
     En büyük tamsayı değeri (yaklaşık 4 milyar) dışında bir dizi boyutu üst sınırı yoktur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizileri kullanma](../../javascript/advanced/using-arrays-javascript.md)