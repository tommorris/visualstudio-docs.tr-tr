---
title: constructor özelliği (Boolean) | Microsoft Docs
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
ms.assetid: b67ca875-23c6-4687-a5ce-1cdd25d1c923
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 091da5342c4713c8eba646a8bd78c315a6a0fa48
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790313"
---
# <a name="constructor-property-boolean"></a>constructor Özelliği (Boolean)
Bir Boole değeri oluşturur işlevi belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
boolean.constructor([[value])  
```  
  
#### <a name="parameters"></a>Parametreler  
 `boolean`  
 Boole değeri adı.  
  
 `value`  
 İsteğe bağlı. Boolean değerini belirtir. Bu sayı 1 veya 0 ' olabilir veya dizeler "true" veya "false".  
  
## <a name="remarks"></a>Açıklamalar  
 `constructor` Özelliği Boolean nesne örneklerini oluşturur işlevi için bir başvuru içeriyor.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek constructor özelliği kullanımını göstermektedir.  
  
```JavaScript  
var x = new Boolean("true");  
  
if (x.constructor == Boolean)  
    document.write("Object is a Boolelan.");  
  
// Output:  
// Object is a Boolean.  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]