---
title: "Mantıksal NOT işleci (!) (JavaScript) | Microsoft Docs"
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
- '!'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Logical NOT operator
- '! operator'
- '! operator, about ! operator'
ms.assetid: 68c3dc71-ae95-4293-9155-67405846d71d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 29c27b9cd670989eb2112de5067e68bd09d76903
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="logical-not-operator--javascript"></a>Mantıksal NOT İşleci (!) (JavaScript)
Mantıksal değilleme bir deyim gerçekleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result = !expression  
```  
  
## <a name="parameters"></a>Parametreler  
 *Sonuç*  
 Herhangi bir değişken.  
  
 *ifade*  
 Herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki tabloda gösterilmektedir nasıl *sonuç* belirlenir.  
  
|Varsa `expression` olduğu|Ardından `result` olduğu|  
|------------------------|----------------------|  
|Doğru|False|  
|False|Doğru|  
  
 Tüm birli işleçleri gibi **!** işleci, ifadeler gibi değerlendirin:  
  
-   Undefined olarak uyguladıysanız veya `null` ifadeleri, bir çalışma zamanı hatası oluşur.  
  
-   Nesneleri dizelere dönüştürülür.  
  
-   Dizeleri sayılara mümkünse dönüştürülür. Aksi durumda, bir çalışma zamanı hatası tetiklenir.  
  
-   Boole değerleri sayılar (0, false ise, true ise 1) kabul edilir.  
  
 İşleci, sonuçta elde edilen sayıya uygulanır.  
  
 İçin **!** işleci, varsa *ifade* sıfır olmayan, olan *sonuç* sıfırdır. Varsa *ifade* sıfır *sonuç* 1'dir.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bitwise NOT işleci (~)](../../javascript/reference/bitwise-not-operator-decrement-tilde-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)