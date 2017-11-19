---
title: "lastIndex özelliği (RegExp) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: lastIndex
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: lastIndex property
ms.assetid: c8ae2a13-6dff-4cbe-b662-aca3d66c2a7f
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5e24fe14d335e1494b13518543f56025625de0b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="lastindex-property-regexp-javascript"></a>lastIndex Özelliği (RegExp) (JavaScript)
Sonraki eşleşmeye başladığı karakterin içinde aranan bir dize döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
RegExp.lastIndex  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu özellik ile ilişkilendirilmiş nesne her zaman geneldir `RegExp` nesnesi.  
  
 `lastIndex` Özelliği sıfır tabanlı, diğer bir deyişle, ilk karakter dizinini sıfır değil. İlk değeri -1'dir. Başarılı bir eşleşme yapıldığında değeri değiştirildi.  
  
 `lastIndex` Tarafından özelliğini değiştirdi `exec` ve **test** yöntemlerinin `RegExp` nesnesi ve `match`, **Değiştir**, ve **bölme**yöntemlerinin `String` nesnesi.  
  
 Değerleri aşağıdaki kurallar geçerli `lastIndex`:  
  
-   Hiçbir eşleşme varsa `lastIndex` -1 olarak ayarlayın.  
  
-   Varsa `lastIndex` dize uzunluğundan büyük **test** ve `exec` başarısız ve `lastIndex` -1 olarak ayarlayın.  
  
-   Varsa `lastIndex` boş dize desen eşleşirse normal ifadeyle eşleşen dize uzunluğu eşittir. Aksi takdirde eşleşme başarısız olur ve `lastIndex` -1 olarak sıfırlanır.  
  
-   Aksi takdirde, `lastIndex` en son eşleşmeden sonraki konumuna ayarlayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `lastIndex` özelliği. Bu işlev bir arama dizesi tekrarlanan ve yazdırır **dizin** ve `lastIndex` dizesindeki her sözcüğün değerleri.  
  
```JavaScript  
function RegExpTest()  
{  
   var ver = Number(ScriptEngineMajorVersion() + "." + ScriptEngineMinorVersion())  
   if (ver < 5.5)  
   {  
      document.write("You need a newer version of JavaScript for this to work");  
      return;  
   }  
  
   var src = "The quick brown fox jumps over the lazy dog.";  
  
   // Create regular expression pattern with a global flag.  
   var re = /\w+/g;  
  
   // Get the next word, starting at the position of lastindex.  
   var arr;  
   while ((arr = re.exec(src)) != null)  
      {  
      // New line:  
      document.write ("<br />");    
      document.write (arr.index + "-" + re.lastIndex + " ");  
      document.write (arr);  
      }  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [RegExp nesnesi](../../javascript/reference/regexp-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Normal ifade sözdizimini (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)