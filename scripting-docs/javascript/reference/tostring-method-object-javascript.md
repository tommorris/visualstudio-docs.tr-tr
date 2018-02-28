---
title: "toString yöntemi (nesne) (JavaScript) | Microsoft Docs"
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
- toString
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- ToString method
ms.assetid: c4ae9da2-60c9-486f-b00a-9df03fda4a35
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 518f988486bb527220884052768e61d099dbd716
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="tostring-method-object-javascript"></a>toString Yöntemi (Nesne) (JavaScript)
Bir nesnenin dize gösterimini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
objectname.toString([radix])  
```  
  
## <a name="parameters"></a>Parametreler  
 `objectname`  
 Gerekli. Bir dize gösterimi aranan bir nesne.  
  
 `radix`  
 İsteğe bağlı. Sayısal değerler dizeleri dönüştürme için bir sayı tabanını belirtir. Bu değer yalnızca sayılar için kullanılır.  
  
## <a name="remarks"></a>Açıklamalar  
 **ToString** yöntemi üyesi olduğu tüm yerleşik [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] nesneleri. Nasıl davranacağını nesne türüne bağlıdır:  
  
|Nesne|Davranış|  
|------------|--------------|  
|Dizi|Öğeleri bir `Array` dizelere dönüştürülür. Virgülle ayrılmış çıkan dizeleri birleşir.|  
|Boole değeri|Boole değeri ise **true**, döndürür "`true`". Aksi takdirde, döndürür "`false`".|  
|Tarih|Tarih değerinin metinsel gösterimini döndürür.|  
|Hata|İlişkili hata iletisini içeren bir dize döndürür.|  
|İşlev|Aşağıdaki biçimde bir dize döndürür nerede *functionname* işlevi adıdır, **toString** yöntemi çağrıldı:<br /><br /> `function functionname( ) { [native code] }`|  
|Sayı|Sayı değerinin metinsel gösterimini döndürür.|  
|Dize|Değerini döndürür `String` nesnesi.|  
|Varsayılan|Döndürür `"[object objectname]"`, burada `objectname` nesne türünün adı.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir **toString** taban bağımsız değişkeniyle yöntemi. Aşağıda gösterilen işlevinin dönüş değeri bir sayı tabanını dönüştürme tablosu verilmiştir.  
  
```JavaScript  
function CreateRadixTable (){  
   var s = "";  
  
   // Create table heading.  
   s += "Hex  Dec  Bin \n";  
  
   for (x = 0; x < 16; x++)  
   {  
      s += "   ";  
  
      // Convert to hexidecimal.  
      s += x.toString(16);  
      s += "     ";  
      if (x < 10) s += "  ";  
  
      // Convert to decimal.  
      s += x.toString(10);  
      s += "     ";  
  
      // Convert to binary.  
      s += x.toString(2);  
      s += "\n";  
   }  
  
   return(s);  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
 **Uygulandığı öğe**: [dizi nesnesi](../../javascript/reference/array-object-javascript.md)&#124; [Boolean nesnesi](../../javascript/reference/boolean-object-javascript.md)&#124; [Tarih nesne](../../javascript/reference/date-object-javascript.md)&#124; [Hata nesnesi](../../javascript/reference/error-object-javascript.md)&#124; [İşlev nesnesi](../../javascript/reference/function-object-javascript.md)&#124; [Sayı nesne](../../javascript/reference/number-object-javascript.md)&#124; [Nesne nesne](../../javascript/reference/object-object-javascript.md)&#124; [Dize nesnesi](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Function deyimi](../../javascript/reference/function-statement-javascript.md)