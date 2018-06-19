---
title: undefined sabiti (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- undefined
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- undefined property
ms.assetid: 2a689d7d-00b0-48fb-9c95-5c2867bde006
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8ba7fa8b160e4f5d954c8d6545da5fae41c2f74b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791666"
---
# <a name="undefined-constant-javascript"></a>tanımlanmamış Sabit (JavaScript)
Hiçbir zaman, henüz başlatılmamış gibi bir değişken tanımlanmış bir değer.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
undefined  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `undefined` Üyesi sabittir `Global` nesne ve komut dosyası altyapısı başlatıldığında kullanılabilir hale gelir. Bir değişken bildirilmiş ancak başlatılmamış zaman değeri olduğu **tanımsız**.  
  
 Bir değişken bildirilmemiş, kendisine karşılaştırılamıyor `undefined`, ancak "undefined" dizeye değişkeninin türü karşılaştırabilirsiniz.  
  
 `undefined` Yararlıdır açıkça sabittir sınama ya da bir değişken tanımsız ayarlama.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `undefined` sabit.  
  
```JavaScript  
// A variable that has not been initialized.  
var declared;  
  
if (declared == undefined)  
    document.write("declared has not been given a value <br/>");  
else  
    document.write("declared has been given a value <br/>");  
  
document.write("typeof declared is " + typeof(declared) + "<br/>");  
  
// An undeclared variable cannot be compared to undefined,  
// so the next line would generate an error.  
// if (notDeclared == undefined);  
  
document.write("typeof notDeclared is " + typeof(notDeclared));  
  
// Output:  
// declared has not been given a value  
// typeof declared is undefined  
// typeof notDeclared is undefined  
```  
  
## <a name="requirements"></a>Gereksinimler  
 `undefined` Özelliği, içinde sunulmuştur [!INCLUDE[jsv55text](../../javascript/reference/includes/jsv55text-md.md)]ve salt okunur hale getirildi [!INCLUDE[jsv9textspecific](../../javascript/reference/includes/jsv9textspecific-md.md)].  
  
 **Uygulandığı öğe**: [genel nesne](../../javascript/reference/global-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [typeof işleci](../../javascript/reference/typeof-operator-decrementjavascript.md)