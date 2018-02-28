---
title: "0... n özellikleri (bağımsız değişkenler) (JavaScript) | Microsoft Docs"
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
- 0...n
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- 0...n properties
ms.assetid: 52857c4b-3d56-4500-93ff-4db4729c2578
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f46c7dafef1cdc27d27f619936349637af172740
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="0n-properties-arguments-javascript"></a>0...n Özellikleri (bağımsız değişkenler) (JavaScript)
Tek tek bağımsız değişkenlerden gerçek değerini döndüren bir **bağımsız değişkenleri** tarafından döndürülen nesne **bağımsız değişkenleri** yürütülen işlevi özelliği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[function.]arguments[[0|1|2|...|n]]  
```  
  
## <a name="parameters"></a>Parametreler  
 *işlevi*  
 İsteğe bağlı. Şu anda yürütülmekte olan adı `Function` nesnesi.  
  
 0, 1, 2, *, n*  
 Gerekli. Negatif olmayan tam sayı 0  *n*  ilk bağımsız değişkeni 0 temsil ettiği ve  *n*  son bağımsız değişkeni temsil eder. Son bağımsız değişkeninin değeri  *n*  olan **arguments.length-1**.  
  
## <a name="remarks"></a>Açıklamalar  
 0 tarafından döndürülen değer. biçimindeki telefon numarasıdır. biçimindeki telefon numarasıdır. yürütülen işlevine geçirilen gerçek değerler n özelliklerdir. Bireysel değişkenleri aslında bir dizi bağımsız değişkenleri, oluşturan **bağımsız değişkenleri** nesne dizi öğeleri erişilen aynı şekilde erişilebilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir **0...**  ***n***özelliklerini **bağımsız değişkenleri** nesnesi. Örnek tam olarak anlamak için işleve bağımsız değişkenlerden biri veya daha fazla geçirin:  
  
```JavaScript  
function ArgTest(){  
   var s = "";  
   s += "The individual arguments are: "  
   for (n = 0; n < arguments.length; n++){  
      s += ArgTest.arguments[n];  
      s += " ";  
   }  
   return(s);  
}  
document.write(ArgTest(1, 2, "hello", new Date()));  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Uygulandığı**: [arguments nesnesi](../../javascript/reference/arguments-object-javascript.md)&#124; [İşlev nesnesi](../../javascript/reference/function-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [length özelliği (bağımsız değişkenler)](../../javascript/reference/length-property-arguments-javascript.md)   
 [length özelliği (işlev)](../../javascript/reference/length-property-function-javascript.md)