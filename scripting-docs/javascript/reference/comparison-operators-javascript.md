---
title: Karşılaştırma işleçleri (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- Comparison
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- comparison operators, script
- greater than operator
- comparison operators
- greater than or equal to operator
- inequity operator
- identity operator
ms.assetid: 084f90f0-d010-47cf-96dd-13d637fc9b68
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 067d570523fc2241b4f2e0442785a49aedb15200
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789161"
---
# <a name="comparison-operators-javascript"></a>Karşılaştırma İşleçleri (JavaScript)
Karşılaştırma sonucu gösteren bir Boole değeri döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
expression1 comparisonoperator expression2  
```  
  
## <a name="parameters"></a>Parametreler  
 `expression1`  
 Herhangi bir ifade.  
  
 `comparisonoperator`  
 Herhangi bir karşılaştırma işleci.  
  
 `expression2`  
 Herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 Dizeleri karşılaştırma zaman [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] dize ifadesinin Unicode karakter değerini kullanır.  
  
 Aşağıdaki türleri ve değerleri bağlı olarak farklı gruplar işleçlerinin nasıl davranacağını açıklar `expression1` ve `expression2`:  
  
 İlişkisel işleçler: `<`, `>`, `<=`,`>=`  
  
-   Her ikisi de dönüştürmeyi denemeden `expression1` ve `expression2` numaraları içine.  
  
-   Her iki ifade dizeleri varsa, bir dize karşılaştırması yapın.  
  
-   Ya da ifade ise `NaN`, dönüş `false`.  
  
-   Negatif sıfır pozitif sıfıra eşittir.  
  
-   Negatif sonsuz kendisi dahil her şeyi küçüktür.  
  
-   Pozitif sonsuzluk kendisi dahil her şeyi büyüktür.  
  
 Eşitlik işleçleri: `==`,`!=`  
  
-   İki ifade türleri farklıysa, dize, sayı veya Boolean dönüştürmeyi dener.  
  
-   `NaN`kendisi de dahil olmak üzere bir şey eşit değil.  
  
-   Negatif sıfır pozitif sıfıra eşittir.  
  
-   `null`her ikisi de eşittir `null` ve `undefined`.  
  
-   Değerleri olarak kabul edilir olmaları durumunda aynı dize, sayısal eşdeğer sayılar, aynı nesne, aynı Boole değerleri eşit veya (varsa farklı türleri) bunlar yüklenen bunlardan biri.  
  
-   Her bir karşılaştırma eşit olarak kabul edilir.  
  
 Kimlik işleçleri: `===`,`!==`  
  
 Tür dönüştürme yapılır dışında bu işleçlere eşitlik işleçleri ile aynı şekilde davranır. Her iki ifade türleri aynı değilseniz, bu ifadeler her zaman geri `false`.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)