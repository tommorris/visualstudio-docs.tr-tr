---
title: "stackTraceLimit özelliği (hata) (JavaScript) | Microsoft Docs"
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
- Error.stackTraceLimit
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- error stack track limit [JavaScript]
- JavaScript error stack
- error stack [JavaScript]
- JavaScript stack trace limit
ms.assetid: 127ef8e8-892e-4263-9ebc-03364af01212
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9af736ee8b385f93b761f1dfa021c23ee5376292
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="stacktracelimit-property-error-javascript"></a>stackTraceLimit Özelliği (Hata) (JavaScript)
Alır veya ayarlar görüntülenecek hata çerçeve sayısı eşdeğerdir yığını izleme sınırı. Varsayılan sınır 10'dur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
Error  
.stackTraceLimit   
```  
  
## <a name="remarks"></a>Açıklamalar  
 Ayarlayabileceğiniz `stackTraceLimit` 0 arasında herhangi bir pozitif değer özelliğine ve `Infinity`. Varsa `stackTraceLimit` özelliği ayarlanmış hiçbir yığın izlemesi hata oluşur zaman 0 olarak gösterilir. Özelliği negatif bir değer veya bir sayısal olmayan bir değere ayarlanırsa, değeri 0 olarak dönüştürülür. StackTraceLimit ayarlanmışsa `Infinity`, tüm yığın gösterilir. Aksi takdirde, `ToUint32` değerini dönüştürmek için kullanılır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, ayarlama ve yığını izleme sınırı alma gösterilmektedir.  
  
```JavaScript  
try  
    {  
    var err = new Error("my error");  
    Error.stackTraceLimit = 7;  
    throw err;  
    }  
catch(e)  
    {  
    document.write ("Error stack trace limit: ")  
    document.write (Error.stackTraceLimit);  
    }  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Internet Explorer 10 ve desteklenen [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar.  
  
 **Uygulandığı öğe**: [hata nesnesi](../../javascript/reference/error-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Description özelliği (hata)](../../javascript/reference/description-property-error-javascript.md)   
 [message özelliği (hata)](../../javascript/reference/message-property-error-javascript.md)   
 [name özelliği (hata)](../../javascript/reference/name-property-error-javascript.md)   
 [stack özelliği (hata)](../../javascript/reference/stack-property-error-javascript.md)