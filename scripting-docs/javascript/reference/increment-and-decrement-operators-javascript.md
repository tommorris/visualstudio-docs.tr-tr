---
title: "Artırma (++) ve azaltma (--) işleçleri (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- --
- ++
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- increment operators, syntax
- ++ operator
- ++ operator, about ++ operator
- decrement operators, syntax
- -- operator
ms.assetid: 49eaf4cf-8818-478d-a429-cdd2ece20811
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 806bd321bb1f81d585a6595b8cf2842571164921
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="increment--and-decrement----operators-javascript"></a>Artırma (++) ve Azaltma (--) İşleçleri (JavaScript)
Artış işleci artırır ve azaltma işleci azaltır tek bir değişkenin değeri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      result = ++variable  
result = --variable  
result = variable++  
result = variable--  
```  
  
## <a name="parameters"></a>Parametreler  
 `result`  
 Herhangi bir değişken.  
  
 `variable`  
 Herhangi bir değişken.  
  
## <a name="remarks"></a>Açıklamalar  
 İşleç değişkeni önce görünürse, ifadenin önce değeri değiştirildi. İşleci sonra değişkeni görünürse, değer ifadesi değerlendirildikten sonra değiştirilir.  Diğer bir deyişle, verilen `j = ++k;`, değeri `j` özgün değeri `k` artı bir; verilen `j = k++;`, değeri `j` özgün değeri `k`, değerini atandığı sonra artar `j`.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)