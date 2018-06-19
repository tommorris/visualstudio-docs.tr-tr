---
title: toLocaleString (sayı) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 42c05252-13c1-4943-b1a4-b33285aeab3e
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9b5e6378ec94e032c908a3502c0324c2a5a91b26
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791762"
---
# <a name="tolocalestring-number"></a>toLocaleString (Sayı)
Bir sayıyı geçerli ya da belirtilen yerel ayar kullanarak bir dizeye dönüştürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
numberObj.toLocaleString([locales][, options])   
```  
  
#### <a name="parameters"></a>Parametreler  
 `numberObj`  
 Gerekli. `Number` Dönüştürülecek nesne.  
  
 `locales`  
 İsteğe bağlı. Bir veya daha fazla dil veya yerel ayar etiketlerini içeren bir yerel dizeler dizisi. Birden fazla yerel ayar dizesi eklerseniz, bunları böylece ilk giriş tercih edilen yerel öncelik sırasına göre azalan sırada listeleyin. Bu parametresini atlarsanız, varsayılan yerel ayar JavaScript çalışma zamanı kullanılır.  
  
 `options`  
 İsteğe bağlı. Karşılaştırma seçenekleri belirten bir veya daha fazla özellikleri içeren bir nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Internet Explorer 11 başlangıç `toLocaleString` kullanan `Intl.NumberFormat` için destek ekleyen dahili yapma karşılaştırmaları için `locales` ve `options` parametreleri. Bu parametreler hakkında daha fazla bilgi için bkz: [INTL.numberformat](../../javascript/reference/intl-numberformat-object-javascript.md).  
  
> [!IMPORTANT]
>  `locales` Ve `options` parametreleri tüm belge modları ve tarayıcı sürümlerinde desteklenmez. Daha fazla bilgi için gereksinimleri bölümüne bakın.  
  
> [!NOTE]
>  Atlarsanız `locales` parametresi, kullanım `toLocaleString` yalnızca bir kullanıcıya; sonuçları görüntülemek için döndürülen sonuç makineye özgü (yöntemi döndürür geçerli yerel ayar) olduğundan hiçbir zaman, bir komut dosyası içindeki değerleri hesaplamak için kullanın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `toLocaleString` hiçbir parametre yöntemi.  
  
```JavaScript  
var n, s;  
n = new Number(100);  
s = "Current locale value is: ";  
s += n.toLocaleString();                 
document.write(s);  
  
// Output:  
// The value 100 as represented by the current locale.  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `toLocaleString` belirtilen yerel ayar ve karşılaştırma seçenekleriyle yöntemi.  
  
```JavaScript  
var number = 123456789;  
var options1 = { style: "percent" };  
var options2 = { style: "currency", currency: "INR" };  
  
document.write(number.toLocaleString("en-US"));  
// 123,456,789  
document.write(number.toLocaleString("ja-JP"));  
// 123,456,789  
document.write(number.toLocaleString("ar-SA", options1));  
// ١٢,٣٤٥,٦٧٨,٩٠٠ %  
document.write(number.toLocaleString("hi-IN", options2));  
// ₹ 12,34,56,789.00  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 `locales`ve `options` Parametreler:  
  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [toLocaleDateString yöntemi (tarih)](../../javascript/reference/tolocaledatestring-method-date-javascript.md)