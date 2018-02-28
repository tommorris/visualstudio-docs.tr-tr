---
title: "message özelliği (hata) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- message
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Message property
ms.assetid: 8cab0392-e0db-4714-827c-47ab04e8b4f2
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9dbd2db6c6d31dc48d90c3b07d2388eacf73ae7a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="message-property-error-javascript"></a>message Özelliği (Hata) (JavaScript)
Bir hata iletisi dizesi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
errorObj.message  
```  
  
## <a name="parameters"></a>Parametreler  
 `errorObj`  
 Gerekli. Örneğini `Error` nesnesi.  
  
## <a name="remarks"></a>Açıklamalar  
 `message` Özelliği, belirli bir hata ile ilişkili bir hata iletisi içeren bir dize döndürür.  
  
 `description` Ve `message` özellikler, aynı işlevselliği sağlar. `description` Özelliği sağlar geriye dönük uyumluluk; `message` özelliği ECMA standart ile uyumludur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir TypeError özel durum oluşturulmasına neden olur ve hata ve kendi ileti adını görüntüler.  
  
```JavaScript  
try  
{  
    // Cause an error.  
    var x = y;  
}  
catch(e)  
{  
    document.write ("Error Message: " + e.message);  
    document.write ("<br />");  
    document.write ("Error Code: ");  
    document.write (e.number & 0xFFFF)  
    document.write ("<br />");  
    document.write ("Error Name: " + e.name);  
}  
```  
  
## <a name="example"></a>Örnek  
 Bu kod çıkışı aşağıdaki gibidir.  
  
```JavaScript  
Error Message: 'y' is undefined  
Error Code: 5009  
Error Name: TypeError  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
 **Uygulandığı öğe**: [hata nesnesi](../../javascript/reference/error-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Description özelliği (hata)](../../javascript/reference/description-property-error-javascript.md)   
 [name özelliği (hata)](../../javascript/reference/name-property-error-javascript.md)