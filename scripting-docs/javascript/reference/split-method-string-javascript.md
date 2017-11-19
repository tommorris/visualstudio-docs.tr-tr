---
title: "split yöntemi (dize) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: split
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: split method
ms.assetid: 7f093336-c887-4efb-b91f-819b6d18a181
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eea90dda2e8e4d52451af247d139eeee44f83917
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="split-method-string-javascript"></a>split Yöntemi (Dize) (JavaScript)
Belirtilen ayırıcıyı kullanarak bir dizeyi alt dizelere böler ve bunları bir dizi olarak döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
stringObj.split([separator[, limit]])  
```  
  
## <a name="parameters"></a>Parametreler  
 `stringObj`  
 Gerekli. `String` Nesne veya dize sabit değeri bölünecek. Bu nesne tarafından değiştirilmez **bölme** yöntemi.  
  
 `separator`  
 İsteğe bağlı. Dize veya bir **normal ifade** karakteri veya dize ayırarak kullanılacak karakterleri tanımlar nesnesi. Atlanırsa, tüm dizeyi içeren tek öğeli bir dizi döndürülür.  
  
 `limit`  
 İsteğe bağlı. Dizide döndürülen öğe sayısını sınırlamak için kullanılan değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sonucu **bölme** yöntemdir her noktada bölünmüş bir dizeler dizisi burada `separator` oluşuyor `stringObj`. `separator` Herhangi bir dizi öğesi bir parçası olarak döndürülmez.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir **bölme** yöntemi.  
  
```JavaScript  
var s = "The quick brown fox jumps over the lazy dog.";  
var ss = s.split(" ");  
for (var i in ss) {  
    document.write(ss[i]);  
    document.write("<br/>");  
}  
  
// Output:   
// The  
// quick  
// brown  
// fox  
// jumps  
// over  
// the  
// lazy  
// dog.  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [dize nesnesi](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [concat yöntemi (dize)](../../javascript/reference/concat-method-string-javascript.md)   
 [RegExp nesnesi](../../javascript/reference/regexp-object-javascript.md)   
 [Normal ifade nesnesi](../../javascript/reference/regular-expression-object-javascript.md)   
 [Normal ifade sözdizimini (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [Kaydırma, kaydırma ve yakınlaştırma örnek uygulaması](http://code.msdn.microsoft.com/ie/Scrolling-panning-and-6834aaf9)