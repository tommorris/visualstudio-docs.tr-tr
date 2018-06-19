---
title: startsWith yöntemi (dize) (JavaScript) | Microsoft Docs
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
ms.assetid: 871def4a-0f96-4675-b6ff-2349f4996511
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 74970a9a3bfe280e91f2df39340732eda8664142
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791552"
---
# <a name="startswith-method-string-javascript"></a>startsWith Yöntemi (Dize) (JavaScript)
Belirtilen dize veya alt dizeyi başka ile başlayıp başlamadığını belirten bir değeri bir dize döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```vb  
  
stringObj.startsWith(str, [, position]);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `stringObj`  
 Gerekli. Arama için dize nesnesi.  
  
 `str`  
 Gerekli. Arama dizesi.  
  
 `position`  
 İsteğe bağlı. 0'den başlayan dize nesnesindeki arama için ilk karakterin konumu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Varsa dize başında `position` , arama dizesi ile başlayan `startsWith` yöntemi döndürür `true`; Aksi takdirde döndürdüğü `false`.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `str` olan bir `RegExp`, `TypeError` atılır.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]