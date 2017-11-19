---
title: "endsWith yöntemi (dize) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: c7d836e3-bc43-4d1b-be60-0a93beb8b7a2
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dc6d57d501f0f100f069522e4b51666918168fa0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="endswith-method-string-javascript"></a>endsWith Yöntemi (Dize) (JavaScript)
Belirtilen dize veya alt dizeyi başka bir işlemle bitip olup olmadığını gösteren bir değeri bir dize döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```vb  
  
stringObj.endsWith(str, [, position]);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `stringObj`  
 Gerekli. Arama için dize nesnesi.  
  
 `str`  
 Gerekli. Arama dizesi.  
  
 `position`  
 İsteğe bağlı. 0'den başlayan dize nesnesindeki arama için ilk karakterin konumu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Varsa dize başında `position` arama dizesiyle biten `endsWith` yöntemi döndürür `true`; Aksi takdirde döndürdüğü `false`.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `str` olan bir `RegExp`, `TypeError` atılır.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]