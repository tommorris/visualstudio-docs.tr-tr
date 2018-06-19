---
title: Şablon dizeleri (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f2e525a5-b0fc-49c3-95a0-641788e5c12a
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d7b6aa430fd4f958c5519093b85d399060b6031a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788786"
---
# <a name="template-strings-javascript"></a>Şablon Dizeleri (JavaScript)
İçinde [!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)], dize değişmez değerleri katıştırılmış ifadeler ile oluşturmak için şablon dizeleri kullanabilirsiniz. Şablon dizeleri, çok satırlı dizeleri için yerleşik destek de sağlar.  
  
 Bir şablonu dizesi oluşturmak için (arka değer olarak da bilinir) Vurgu kullanmak yerine tek veya çift tırnak dizeyi çift tırnak içine ('). Aşağıdaki kod örneğinde basit şablon dizesini gösterir.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Şablon dizeleri, satır sonları satır besleme karakteriyle (\n) kullanılmasına gerek kalmadan ekleyebilirsiniz.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 $ Karakteri şablon dizesini yer tutucularını belirtmek için kullanılır. Söz dizimi ${*ifade*}, burada *ifade* tüm JavaScript gibi bir değişken veya işlev, aşağıdaki örnekte gösterildiği gibi ifadesidir.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
 Çağrılan işlev şablonu dizesi bağımsız değişkenlerini kullanarak şablonu dize değerini değiştirmek izin etiketli şablon işlevleri. İlk bağımsız değişkeni dize değişmez değerleri, içerdiği, şablonu dizesi ifadeleri tarafından ayrılmış bir dizi ve ikinci bağımsız değişkeni bir dizi (bir [Rest parametresi](../../javascript/functions-javascript.md)) şablonu dizesi ifadeleri değerlerini içerir.  
  
 Aşağıdaki örnekte, etiketli şablon işlevi buildURL bir URL oluşturmak için kullanılır. Sözdizimi şablon dizeyle hemen ardından işlev adı kullanmaktır.  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
 Geçirilen ham dize değerlerini erişmesi gerekiyorsa, ilk bağımsız değişken geçirildi etiketli şablon işlevi destekler için bir `raw` geçirilen dizeleri ham dize biçiminde döndüren özelliği.  
  
```  
function buildURL(strArray, ...valArray) {  
    console.log(strArray.raw);  
}  
  
var lang = "en-us";  
var a = "library";  
var b = "dn771551.aspx";  
  
// Call the tagged template function.  
var url = buildURL`http://msdn.microsoft.com/${lang}/${a}/${b}`;  
  
// Ouput:  
// http://msdn.microsoft.com/  
// /  
// en-us  
// library  
```  
  
> [!NOTE]
>  Aynı zamanda [String.raw](../../javascript/reference/string-raw-function-javascript.md) işlevi şablon dizesini ham dize biçiminde döndürecek şekilde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JavaScript dil başvurusu](../../javascript/javascript-language-reference.md)   
 [Gelişmiş JavaScript](../../javascript/advanced/advanced-javascript.md)