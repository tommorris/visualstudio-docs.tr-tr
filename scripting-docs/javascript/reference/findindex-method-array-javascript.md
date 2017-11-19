---
title: "findIndex yöntemi (dizi) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 3a200cf0-db67-4c7b-89f8-5e9f5dc1a926
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c8da475b776e1c04e4fe5bfc7062318cfec952c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="findindex-method-array-javascript"></a>findIndex Yöntemi (Dizi) (JavaScript)
Sınama geri çağırma fonksiyonu içinde belirtilen ölçütleri karşılar ilk dizi öğesi için bir dizin değeri döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
arrayObj.findIndex(callbackfn [, thisArg]);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `arrayObj`  
 Gerekli. Dizi nesnesi.  
  
 `callbackfn`  
 Gerekli. Dizideki her öğe test etmek için geri çağırma işlevi.  
  
 `thisArg`  
 İsteğe bağlı. Belirtir `this` nesnesinde geri çağırma işlevi. Belirtilmezse, `this` nesne tanımlanmadı.  
  
## <a name="remarks"></a>Açıklamalar  
 `findIndex` Öğenin dönene kadar artan düzende, dizideki her öğe için bir kez geri çağırma işlevini çağırır `true`. Bir öğenin true döndürür hemen `findIndex` true değerini döndürür öğenin dizini değerini döndürür. Dizide öğe true dönerseniz `findIndex` -1 döndürür.  
  
 `findIndex`dizi nesnesi değiştirmediğini.  
  
## <a name="callback-function-syntax"></a>Geri Çağırma İşlevi Sözdizimi  
 Geri çağırma işlevinin sözdizimi aşağıdaki gibidir:  
  
 `function callbackfn(value, index, thisArg)`  
  
 En çok üç parametre kullanarak geri çağırma işlevini bildirebilirsiniz.  
  
 Geri çağırma işlevi parametreleri aşağıdaki gibidir.  
  
|Geri çağırma bağımsız değişkeni|Tanım|  
|-----------------------|----------------|  
|`value`|Dizi öğesinin değeri.|  
|`index`|Dizi öğesinin sayısal dizini.|  
|`arrayObj`|Geçmesi için dizi nesnesi.|  
  
## <a name="example"></a>Örnek  
 Dizideki her öğe 2'ye eşit olup olmadığını aşağıdaki örnekte, geri çağırma işlevi sınar.  
  
```JavaScript  
[1,2,3].findIndex(function(x) { x == 2; });  
// Returns an index value of 1.  
  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, her öğe test etmek için oka sözdizimini kullanır. Bu örnekte, öğe dönmek `true`, ve `findIndex` -1 döndürür.  
  
```  
[1,2,3].findIndex(x => x == 4);  
// Returns an index value of -1.   
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]