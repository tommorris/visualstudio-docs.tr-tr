---
title: fill yöntemi (dizi) (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 11526627-c0bb-4157-a8c4-0a039079b4a1
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4546bafb3fa3a8c242b8b7ef4ef2863ea86bf179
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790451"
---
# <a name="fill-method-array-javascript"></a>fill Yöntemi (Dizi) (JavaScript)
Belirli bir değerle bir dizi doldurur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
arrayObj.fill(value [ , start [ , end ] ]);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `arrayObj`  
 Gerekli. Dizi nesnesi.  
  
 `value`  
 Gerekli. Dizi doldurmak için kullanılan değer.  
  
 `start`  
 İsteğe bağlı. Dizi değerleri doldurmak için kullanılan başlangıç dizini. Varsayılan değer 0’dır.  
  
 `end`  
 İsteğe bağlı. Dizi değerleri doldurmak için kullanılan bitiş dizini. Varsayılan değer uzunluğu özelliğidir `this` nesnesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `start` negatif `start` olarak işlem görür `length` + `start`, burada `length` dizi uzunluğu. Varsa `end` negatif `end` olarak işlem görür `length` + `end`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örnekleri bir dizi değerlerle doldurun.  
  
```JavaScript  
[0, 0, 0].fill(7, 1);  
// Array contains [0,7,7]  
  
[0, 0, 0].fill(7);  
// Array contains [7,7,7]  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]