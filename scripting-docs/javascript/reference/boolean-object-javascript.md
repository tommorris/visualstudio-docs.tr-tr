---
title: Boolean nesnesi (JavaScript) | Microsoft Docs
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
- boolean_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Boolean object
- Boolean data type, Boolean object
ms.assetid: d67748f2-7bf5-4889-8269-e777616cc5f0
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 20695376e4935cf6ddc34f30e373df19575ece3f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789041"
---
# <a name="boolean-object-javascript"></a>Boolean Nesnesi (JavaScript)
Yeni bir Boole değeri oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
boolObj = new Boolean([boolValue])  
```  
  
## <a name="parameters"></a>Parametreler  
 `boolObj`  
 Gerekli. Değişken adına `Boolean` nesne atanır.  
  
 `boolValue`  
 İsteğe bağlı. Yeni nesne için ilk Boole değeri. Varsa `boolvalue` atlanmış ya da `false`, 0, `null`, `NaN`, veya boş bir dize Boolean nesnesinin başlangıç değeri `false`. Aksi takdirde, başlangıç değeridir `true`.  
  
## <a name="remarks"></a>Açıklamalar  
 `Boolean` Nesnesidir Boole veri türü için sarmalayıcı. [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]örtük olarak kullanan `Boolean` Boole veri türü için dönüştürülen her nesne bir `Boolean` nesnesi.  
  
 Nadiren örneği `Boolean` açıkça nesne.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda özelliklerini `Boolean` nesnesi.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[constructor özelliği](../../javascript/reference/constructor-property-boolean.md)|Bir Boole değeri oluşturur işlevi belirtir.|  
|[prototype özelliği](../../javascript/reference/prototype-property-boolean.md)|Prototip başvuru için bir Boole değeri döndürür.|  
  
<a name="js56jsobjarraymeth"></a>   
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `Boolean` nesnesi.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[toString yöntemi](../../javascript/reference/tostring-method-boolean-1.md)|Bir Boole değeri bir dize gösterimini döndürür.|  
|[valueOf yöntemi](../../javascript/reference/valueof-method-boolean.md)|Boole değeri bir başvuru alır.|  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]