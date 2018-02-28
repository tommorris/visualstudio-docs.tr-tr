---
title: JSON nesnesi (JavaScript) | Microsoft Docs
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
- JSON
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- JSON object
ms.assetid: 0279a0e0-70bf-451a-a78e-0da4e2fdeb9a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5310132368f665c6734c469a67636d33a08858d4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="json-object-javascript"></a>JSON Nesnesi (JavaScript)
Dönüştürme işlevleri sağlayan bir iç nesne [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] değerleri JavaScript nesne gösterimi (JSON) biçimine gelen ve giden. `JSON.stringify` İşlevi serileştiren bir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] JSON metin değeri. `JSON.parse` İşlevi çıkarır üretmek için JSON metni bir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] değeri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
JSON.[method]  
  
```  
  
## <a name="parameters"></a>Parametreler  
 `Method`  
 Gerekli. Yöntemlerinden birini adını `JSON` nesnesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Oluşturamazsınız bir `JSON` kullanarak nesne `new` işleci. Bunu yapmayı denerseniz bir hata oluşur. Ancak, geçersiz kılma veya değiştirebileceğiniz `JSON` nesnesi.  
  
 Komut dosyası motoru oluşturur `JSON` nesne altyapısı yüklendiğinde. Yöntemleri, komut dosyanız için her zaman kullanılabilir.  
  
 İç kullanılacak `JSON` nesne, bunu başka bir işlemle geçersiz kılmaz olduğundan emin olun `JSON` komut dosyasında tanımlı nesne. Varlığını mevcut betik deyimleri değiştirmeniz gerekebilir bir `JSON` bu deyimleri farklı değerlendirecek çünkü nesne. Bu, aşağıdaki örnekte gösterilmiştir.  
  
```JavaScript  
if (!this.JSON) {  
    // JSON object does not exist.  
    }  
```  
  
 Önceki örnekte, `!this.JSON` false olarak değerlendirir [!INCLUDE[jsv58text](../../javascript/reference/includes/jsv58text-md.md)]. Bu nedenle, içinde kod `if` deyimi yürütülmez.  
  
## <a name="functions"></a>İşlevler  
 [JSON.parse işlevi](../../javascript/reference/json-parse-function-javascript.md)  
  
 [JSON.stringify işlevi](../../javascript/reference/json-stringify-function-javascript.md)  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv58](../../javascript/reference/includes/jsv58-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [toJSON yöntemi (tarih)](../../javascript/reference/tojson-method-date-javascript.md)   
 [JavaScript nesneleri](../../javascript/reference/javascript-objects.md)   
 [Hub şablon örnek uygulama (Windows mağazası)](http://code.msdn.microsoft.com/Hub-template-sample-with-4b70002d)