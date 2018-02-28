---
title: "Number özelliği (hata) (JavaScript) | Microsoft Docs"
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
- Number
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Number property
ms.assetid: 8697e20b-a2b0-4e26-85c0-ab07ddfe8281
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bbc229e7d0572e1a3dbed056b344da7ff9ce7292
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="number-property-error-javascript"></a>number Özelliği (Hata) (JavaScript)
Döndürür veya belirli bir hata ile ilişkili sayısal değerini ayarlar. `Error` Nesnesinin varsayılan özelliğidir **numarası**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
object  
.number [= errorNumber]  
```  
  
## <a name="parameters"></a>Parametreler  
 *Nesne*  
 Herhangi bir örneğine `Error` nesnesi.  
  
 *HataNumarası*  
 Bir hata temsil eden bir tamsayı.  
  
## <a name="remarks"></a>Açıklamalar  
 Hata numarası, 32 bit bir değerdir. Tesis kodu üst 16 bit sözcüktür ve alt word hata kodudur. Hata kodu belirlemek için `&` (bit düzeyinde ve) number özelliği onaltılık sayı ile birleştirme işleci `0xFFFF`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir özel durum oluşturulmasına neden olur ve hata numarasından türetilmiş hata kodunu görüntüler.  
  
```JavaScript  
try  
    {  
    // Cause an error.  
    var x = y;  
    }  
catch(e)  
    {  
    document.write ("Error Code: ");  
    document.write (e.number & 0xFFFF)  
    document.write ("<br />");  
  
    document.write ("Facility Code: ")  
    document.write(e.number>>16 & 0x1FFF)  
    document.write ("<br />");  
  
    document.write ("Error Message: ")  
    document.write (e.message)  
    }  
```  
  
## <a name="example"></a>Örnek  
 Bu kod çıkışı aşağıdaki gibidir.  
  
```JavaScript  
Error Code: 5009  
Facility Code: 10  
Error Message: 'y' is undefined  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
 **Uygulandığı öğe**: [hata nesnesi](../../javascript/reference/error-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Description özelliği (hata)](../../javascript/reference/description-property-error-javascript.md)   
 [message özelliği (hata)](../../javascript/reference/message-property-error-javascript.md)   
 [name özelliği (hata)](../../javascript/reference/name-property-error-javascript.md)