---
title: "join yöntemi (dizi) (JavaScript) | Microsoft Docs"
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
- join
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Join method
- concatenating strings, join method
- arrays [Visual Studio], joining
ms.assetid: 20f8fde1-014b-488e-9008-464a86e6b21f
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4591b12b3556384fef3e367d20cf9545d2f3dedd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="join-method-array-javascript"></a>join Yöntemi (Dizi) (JavaScript)
Belirtilen ayırıcı dizeyle ayrılmış bir dizinin tüm öğeleri ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
arrayObj.join([separator])   
```  
  
## <a name="parameters"></a>Parametreler  
 `arrayObj`  
 Gerekli. Bir `Array` nesnesi.  
  
 `separator`  
 İsteğe bağlı. Sonraki sonuç olarak bir dizi bir öğe ayırmak için kullanılan bir dize `String`. Atlanırsa, dizi öğeleri virgül ile ayrılır.  
  
## <a name="remarks"></a>Açıklamalar  
 Dizinin herhangi bir öğe ise **tanımsız** veya `null`, boş bir dize kabul edilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir **birleştirme** yöntemi.  
  
```JavaScript  
var a, b;  
a = new Array(0,1,2,3,4);  
b = a.join("-");  
document.write(b);  
  
// Output:  
// 0-1-2-3-4  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize nesnesi](../../javascript/reference/string-object-javascript.md)