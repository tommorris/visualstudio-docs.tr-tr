---
title: "localeCompare yöntemi (dize) (JavaScript) | Microsoft Docs"
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
- localeCompare
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- localeCompare method
ms.assetid: 66914079-12dd-4393-a84c-c05f58231c36
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 056a440d26c4ebf48bd762968fa32ea1efdfb443
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="localecompare-method-string-javascript"></a>localeCompare Yöntemi (Dize) (JavaScript)
İki dizeyi geçerli yerel ayarda eşdeğer olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
stringVar.localeCompare(stringExp[, locales][, options])   
```  
  
## <a name="parameters"></a>Parametreler  
 `stringVar`  
 Gerekli. Karşılaştırılacak ilk dize.  
  
 `stringExp`  
 Gerekli. Karşılaştırılacak ikinci dize.  
  
 `locales`  
 İsteğe bağlı. Bir veya daha fazla dil veya yerel ayar etiketlerini içeren bir yerel dizeler dizisi. Birden fazla yerel ayar dizesi eklerseniz, bunları böylece ilk giriş tercih edilen yerel öncelik sırasına göre azalan sırada listeleyin. Bu parametresini atlarsanız, varsayılan yerel ayar JavaScript çalışma zamanı kullanılır. Bu parametre için uymalıdır [BCP 47](http://tools.ietf.org/html/rfc5646) standartları; bkz: [INTL.collator nesnesi](../../javascript/reference/intl-collator-object-javascript.md) Ayrıntılar için.  
  
 `options`  
 İsteğe bağlı. Karşılaştırma seçenekleri belirten bir veya daha fazla özellikleri içeren bir nesne. bkz: [INTL.collator nesnesi](../../javascript/reference/intl-collator-object-javascript.md) Ayrıntılar için.  
  
## <a name="remarks"></a>Açıklamalar  
 Karşılaştırma dizeleri için ya da belirttiğiniz `String` nesneleri veya dize değişmez değerleri.  
  
 Internet Explorer 11 başlangıç `localeCompare` kullanan `Intl.Collator` dahili karşılaştırmaları yapmak için hangi için destek ekler nesne `locales` ve `options` parametreleri. Bu parametreler hakkında daha fazla bilgi için bkz: [INTL.collator](../../javascript/reference/intl-collator-object-javascript.md) ve [Intl.Collator.compare](../../javascript/reference/compare-property-intl-collator.md).  
  
> [!IMPORTANT]
>  `locales` Ve `options` parametreleri tüm belge modları ve tarayıcı sürümlerinde desteklenmez. Daha fazla bilgi için gereksinimleri bölümüne bakın.  
  
 `localeCompare` Yöntemi gerçekleştirir yerel ayara duyarlı dize karşılaştırması `stringVar` ve `stringExp` ve aşağıdakilerden birini sonuçları, sistem varsayılan yerel sıralama düzeni bağlı olarak döndürür:  
  
-   -1 IF `stringVar` önce sıralar `stringExp`.  
  
-   + 1 IF `stringVar` sonra sıralar `stringExp`.  
  
-   0 (sıfır) iki dizeyi eşdeğer ise.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu nasıl kullanılacağını gösterir `localeCompare`.  
  
```JavaScript  
var str1 = "def";  
var str2 = "abc"  
  
document.write(str1.localeCompare(str2) + "<br/>");  
  
// Output: 1  
var str3 = "ghi";  
  
document.write(str1.localeCompare(str3)+ "<br/>");  
  
// Output: -1  
var str4 = "def";  
  
document.write(str1.localeCompare(str4));  
  
// Output: 0  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu nasıl kullanılacağını gösterir `localeCompare` Almanca (Almanya) yerel ayar ile.  
  
```JavaScript  
var str1 = "a";  
var str2 = "b";  
  
document.write(str1.localeCompare(str2, "de-DE"));  
  
// Output  
// - 1  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `localeCompare` Almanca (Almanya) yerel ayar ve Almanca Telefon rehberi için sıralama düzenini belirten bir yerel ayarlara özgü uzantısı ile. Bu örnek, yerel ayarlara özgü farklılıkları gösterir.  
  
```JavaScript  
var arr = ["ä", "ad", "af", "a"];  
  
document.write(arr[0].localeCompare(arr[1], "de-DE-u-co-phonebk"));  // Returns 1  
document.write (arr[0].localeCompare(arr[2], "de-DE-u-co-phonebk"));  // Returns -1  
document.write (arr[0].localeCompare(arr[3], "de-DE-u-co-phonebk"));  // Returns 1  
  
document.write (arr[0].localeCompare(arr[1], "de-DE"));  // Returns -1  
document.write (arr[0].localeCompare(arr[2], "de-DE"));  // Returns -1  
document.write (arr[0].localeCompare(arr[3], "de-DE"));  // Returns 1  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 `locales`ve `options` Parametreler:  
  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [toLocaleString yöntemi (nesne)](../../javascript/reference/tolocalestring-method-object-javascript.md)