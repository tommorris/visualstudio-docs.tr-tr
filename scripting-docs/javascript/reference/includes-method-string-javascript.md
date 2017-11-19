---
title: "includes yöntemi (dize) (JavaScript) | Microsoft Docs"
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
ms.assetid: 2639e4e5-23ba-424a-80ea-be067a4cd65e
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 848143b64d3e32452aea41f08b6f5c57879d3e17
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="includes-method-string-javascript"></a>includes Yöntemi (Dize) (JavaScript)
Geçirilen dize dize nesnesinde yer alan olup olmadığını gösteren bir Boole değeri döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
stringObj.includes(substring [, position]);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `stringObj`  
 Gerekli. Sınanacak dize nesnesi.  
  
 `substring`  
 Gerekli. Sınama dizesi.  
  
 `position`  
 İsteğe bağlı. 0'dan başlayarak dize nesnesindeki karşı test etmek için ilk karakterin konumu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçirilen dize dize nesnesinde yer alıyorsa `includes` yöntemi döndürür `true`; Aksi takdirde döndürdüğü `false`.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
  
```JavaScript  
// Returns true   
"abcde".includes("cd")  
"abcde".includes("cd", 2)  
  
// Returns false  
"abcde".includes("CD")  
"abcde".includes("cd", 3)  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]