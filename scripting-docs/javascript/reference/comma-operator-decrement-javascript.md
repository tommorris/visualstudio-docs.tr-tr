---
title: "Virgül işleci (,) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '%2C'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: comma operator
ms.assetid: 699fa0bf-cd0a-45ee-a291-2fbed4ecd470
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2cb504beefc5ce4c260ec8296e2cf097e17d349e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="comma-operator--javascript"></a>Virgül İşleci (,) (JavaScript)
Sıralı olarak yürütülecek iki ifadeye neden olur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
expression1, expression2  
```  
  
## <a name="parameters"></a>Parametreler  
 `expression1`  
 Herhangi bir ifade.  
  
 `expression2`  
 Herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 `,` İşleci soldan sağa sırayla yürütülecek ifadeleri neden olur. Yaygın kullanım `,` işlecidir artırma ifadesinde bir `for` döngü. Örneğin:  
  
```JavaScript  
j=25;  
for (i = 0; i < 10; i++, j++)  
{  
   k = i + j;  
}  
```  
  
 `for` Deyimi her bir döngü geçiş işleminin sonunda yürütülecek yalnızca tek bir ifade sağlar. `,` İşleci her iki değişken artar şekilde tek bir ifade kabul edilmesi birden çok ifadeleri sağlar.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [for deyimi](../../javascript/reference/for-statement-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)