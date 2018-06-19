---
title: Number.isNaN işlevi (sayı) (JavaScript) | Microsoft Docs
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
ms.assetid: 2d9813d6-ec9c-433b-b060-8e3c3ff62ca4
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7c11abe2dd2fc70431800d31f4c44279a88cd75d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791228"
---
# <a name="numberisnan-function-number-javascript"></a>Number.isNaN İşlevi (Sayı) (JavaScript)
Bir değer ayrılan değeri olup olmadığını belirten bir Boole değeri döndürür `NaN` (sayı değil).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Number.isNaN(numValue)   
```  
  
#### <a name="parameters"></a>Parametreler  
 `numValue`  
 Gerekli. Karşı test edilecek değer `NaN`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`değer dönüştürülüp varsa `Number` türü `NaN`, aksi takdirde `false`.  
  
## <a name="remarks"></a>Açıklamalar  
 Dönüş değerleri test etmek için bu yöntemi kullanın `parseInt` ve `parseFloat` yöntemleri.  
  
 `Number.isNaN`genel sorunları düzeltir `isNaN` işlevi. `Number.isNaN`tür bağımsız değişkeni sayı ile karşılaştıran sonra dönüştürür `NaN`. Sonuç olarak döndüren `true` geçirilen bağımsız değişken tam olarak aynı değeri varsa ve yalnızca ise `NaN`. Genel `isNaN` işlevi bağımsız değişkeninin değerini döndüren sayı olmayan değerleri için yol açabilecek karşılaştırma önce numarasını yazın dönüştürür `true`, değil döndürebilir ancak `true` için `Number.isNaN`.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
 **Uygulandığı öğe**: [sayı nesnesi](../../javascript/reference/number-object-javascript.md)  
  
## <a name="example"></a>Örnek  
  
```JavaScript  
// Returns true.  
Number.isNaN(NaN);  
Number.isNaN(Number.NaN);  
Number.isNaN(0 / 0);  
  
// Returns false.  
Number.isNaN(100);  
// Returns false.  
// Strings are converted to numbers and return false.  
Number.isNaN("100");  
Number.isNaN("ABC");  
Number.isNaN("10C");  
Number.isNaN("abc123");  
  
```