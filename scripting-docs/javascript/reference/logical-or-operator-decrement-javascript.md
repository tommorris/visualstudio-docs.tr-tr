---
title: "Mantıksal OR işleci (|) (JavaScript) | Microsoft Docs"
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
- '||'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '|| operator'
- logical OR operator
ms.assetid: 95295331-6269-4311-8391-dc1c68e116ab
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 80c8e1bcae57e13642a0c77ae75c7c2aac58ace6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="logical-or-operator--javascript"></a>Mantıksal OR İşleci (||) (JavaScript)
Mantıksal ayrım iki ifadeleri gerçekleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result = expression1 || expression2  
```  
  
## <a name="parameters"></a>Parametreler  
 *Sonuç*  
 Herhangi bir değişken.  
  
 *İfade1*  
 Herhangi bir ifade.  
  
 *İfade2*  
 Herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 İçin veya her ikisi ifadeleri değerlendirin varsa **True**, *sonuç* olan **doğru**. Aşağıdaki tabloda gösterilmektedir nasıl *sonuç* belirlenir:  
  
|Varsa `expression1` olduğu|Ve `expression2` olduğu|`result` Olduğu|  
|-------------------------|--------------------------|---------------------|  
|Doğru|Doğru|Doğru|  
|Doğru|False|Doğru|  
|False|Doğru|Doğru|  
|False|False|False|  
  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]Boole olmayan değerlerini Boolean değerlerine dönüştürmek için aşağıdaki kuralları kullanır:  
  
-   Tüm nesneler true olarak kabul edilir.  
  
-   Boş ve yalnızca, dizeleri false olarak kabul edilir.  
  
-   `null`ve tanımlanmamış yanlış olarak değerlendirilir.  
  
-   False ise ve yalnızca numaralarıdır, 0 olur.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)