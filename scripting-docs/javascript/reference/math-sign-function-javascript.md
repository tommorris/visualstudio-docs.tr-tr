---
title: Math.sign işlevi (JavaScript) | Microsoft Docs
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
ms.assetid: 8b462020-ceff-4947-8dd1-c78e6aff8d98
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2cae32118f2265e02c67592facff8e49e8edd633
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790919"
---
# <a name="mathsign-function-javascript"></a>Math.sign İşlevi (JavaScript)
Oturum açma sayısı pozitif, negatif veya 0 olup olmadığını belirten bir sayı döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Math.sign(number)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `number` bağımsız değişkeni olan sayısal ifadenin oturum gereklidir.  
  
 Dönüş değeri aşağıdakilerden biridir:  
  
-   `NaN`, varsa `number` olan `NaN`.  
  
-   -0 ise `number` : - 0.  
  
-   + 0, varsa `number` olan + 0.  
  
-   -1, varsa `number` negatif değil - 0.  
  
-   + 1, varsa `number` pozitif ve + 0.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]