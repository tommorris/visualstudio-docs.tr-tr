---
title: toLocaleLowerCase yöntemi (dize) (JavaScript) | Microsoft Docs
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
- toLocaleLowerCase
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toLocaleLowerCase method
ms.assetid: add894d3-d14a-4dbc-a9b9-7ad1d3a2e581
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 642ced387e0d3b4cf763767ec147d6160ed7d36b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791651"
---
# <a name="tolocalelowercase-method-string-javascript"></a>toLocaleLowerCase Yöntemi (Dize) (JavaScript)
Küçük harf için tüm alfabetik karakterler, ana bilgisayar ortamı geçerli yerel ayar dikkate alarak dönüştürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
stringVar.toLocaleLowerCase( )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `stringVar` başvurusu olan bir `String` nesne veya dize sabit değeri.  
  
 `toLocaleLowerCase` Yöntemi ana bilgisayar ortamı geçerli yerel ayar dikkate alarak, bir dizedeki karakter dönüştürür. Çoğu durumda, aynı sonucu olarak sonucudur `toLowerCase` yöntemi. Bir dil için kuralları ile normal Unicode durum eşlemeleri çakışırsa sonuçları farklılık gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Uygulandığı öğe**: [dize nesnesi](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [toLocaleUpperCase yöntemi (dize)](../../javascript/reference/tolocaleuppercase-method-string-javascript.md)   
 [toLowerCase yöntemi](../../javascript/reference/tolowercase-method-javascript.md)