---
title: "Çıkarma işleci (-) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '-'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '- operator, about - operator'
- '- operator'
- negation operator
- subtraction operator, syntax
- arithmetic operators, subtraction
- operators, subtraction
ms.assetid: cd0681d3-15cd-49fe-b4dd-e087de55d778
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb79aab0a57c733871dbfc73ac96c7ddbf4db37c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="subtraction-operator---javascript"></a>Çıkarma İşleci (-) (JavaScript)
Başka bir tek bir ifade değeri çıkarır veya tek bir ifade, tekli değilleme sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result = number1 - number2;  
```  
  
## <a name="parameters"></a>Parametreler  
 *Sonuç*  
 Herhangi bir sayısal değişkeni.  
  
 `number`  
 Herhangi bir sayısal ifade.  
  
 `number1`  
 Herhangi bir sayısal ifade.  
  
 `number2`  
 Herhangi bir sayısal ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 Sözdizimi 1  **-**  işlecidir iki sayı arasındaki farkı bulmak için kullanılan aritmetik çıkarma işleci. Sözdizimi 2'de,  **-**  işleci tekli değilleme işleci bir ifadenin negatif değerini belirtmek için kullanılır.  
  
 Sözdizimi 2 için tüm birli işleçleri için olduğu gibi ifadeler gibi değerlendirilir:  
  
-   Undefined olarak uyguladıysanız veya `null` ifadeleri, bir çalışma zamanı hatası oluşur.  
  
-   Nesneleri dizelere dönüştürülür.  
  
-   Dizeleri sayılara mümkünse dönüştürülür. Aksi durumda, bir çalışma zamanı hatası tetiklenir.  
  
-   Boole değerleri sayılar (0, false ise, true ise 1) kabul edilir.  
  
 İşleci, sonuçta elde edilen sayıya uygulanır. Sözdizimi sonuç sayısı sıfır, değilse 2'deki *sonuç* tersine, ile elde edilen sayıya eşit işaretidir. Sonuçta elde edilen sayı sıfırsa, *sonuç* sıfırdır.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıkarma atama işleci (-)](../../javascript/reference/subtraction-assignment-operator-decrement-equal-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)