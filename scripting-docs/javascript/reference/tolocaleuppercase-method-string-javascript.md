---
title: toLocaleUpperCase yöntemi (dize) (JavaScript) | Microsoft Docs
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
- toLocaleUpperCase
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toLocaleUpperCase method
ms.assetid: e927adb6-475e-44b2-91f7-cedda10a39b0
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 07a89560dde0319598da30fc3451524112b99eac
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791639"
---
# <a name="tolocaleuppercase-method-string-javascript"></a>toLocaleUpperCase Yöntemi (Dize) (JavaScript)
Tüm alfabetik karakterler büyük harf, konak dikkate alınması Dönüştürülen ortamı geçerli yerel burada kaldırılmış bir dize döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
stringVar.toLocaleUpperCase( )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `stringVar` başvurusu olan bir `String` nesne veya dize sabit değeri.  
  
 `toLocaleUpperCase` Yöntemi ana bilgisayar ortamı geçerli yerel ayar dikkate alarak, bir dizedeki karakter dönüştürür. Çoğu durumda, aynı sonucu olarak sonucudur `toUpperCase` yöntemi. Bir dil için kuralları ile normal Unicode durum eşlemeleri çakışırsa sonuçları farklılık gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Uygulandığı öğe**: [dize nesnesi](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [toLocaleLowerCase yöntemi (dize)](../../javascript/reference/tolocalelowercase-method-string-javascript.md)   
 [toUpperCase yöntemi (dize)](../../javascript/reference/touppercase-method-string-javascript.md)