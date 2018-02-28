---
title: "Mantıksal AND işleci (&amp;&amp;) (JavaScript) | Microsoft Docs"
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
- '&&'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- logical AND operator
- '&& operator'
ms.assetid: 4714dea9-1999-444a-8acd-72f0851e4f65
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2107eb89c5ca964cf08172050b49307cb150590f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="logical-and-operator-ampamp-javascript"></a>Mantıksal AND işleci (&amp;&amp;) (JavaScript)
Mantıksal ve işlecini iki ifadeleri gerçekleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result = expression1 && expression2   
```  
  
## <a name="parameters"></a>Parametreler  
 `result`  
 Herhangi bir değişken.  
  
 `expression1`  
 Herhangi bir ifade.  
  
 `expression2`  
 Herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `expression1` değerlendiren `false`, `result` olan `expression1`. Aksi takdirde, `result` olan `expression2`. Sonuç olarak, işlem döndürür `true` her iki işlenen doğruysa; Aksi takdirde, döndürür `false`.  
  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]Boole olmayan değerlerini Boolean değerlerine dönüştürmek için aşağıdaki kuralları kullanır:  
  
-   Tüm nesneler olduğu kabul edilir `true`.  
  
-   Dizeleri olarak değerlendirilir `false` boş ise.  
  
-   `null`ve `undefined` olduğu kabul edilir `false`.  
  
-   Bir sayı `false` sıfır ise.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)