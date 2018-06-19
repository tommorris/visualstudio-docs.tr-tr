---
title: Object.is işlevi (JavaScript) | Microsoft Docs
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
ms.assetid: 6e2f6c6d-7cd2-47c4-a513-3ba53988d27d
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 36d4c281fdafbfacb0b1f6061ef4a90bfac99234
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791120"
---
# <a name="objectis-function-javascript"></a>Object.is İşlevi (JavaScript)
İki değer aynı değer olup olmadığını belirten bir değer döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
Object.is(value1, value2)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `value1`  
 Gerekli. Sınanacak ilk değer.  
  
 `value2`  
 Gerekli. Sınanacak ikinci değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`aynı değer değeridir Aksi takdirde `false`.  
  
## <a name="remarks"></a>Açıklamalar  
 Aksine == işleci, `Object.is` herhangi bir türü değerleri test edilirken coerce değil.  
  
 Tarafından uygulanan karşılaştırma `Object.is` tarafından uygulanan karşılaştırma benzer === hariç işleci `Object.is` değerlendirir `Number.isNaN` aynı değere olarak `NaN`. Bu ayrıca davranır + 0 ve - 0 farklı değerler olarak.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]