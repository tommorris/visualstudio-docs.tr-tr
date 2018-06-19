---
title: length özelliği (dizi) (JavaScript) | Microsoft Docs
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
- length Property
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Array object
- Length property
- length property (array)
ms.assetid: e1c6377c-2e84-440a-9660-f1f512e4a938
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6e69fd5387b1d7430491b1693dec07581f165cc9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790886"
---
# <a name="length-property-array-javascript"></a>length Özelliği (Dizi) (JavaScript)
Alır veya ayarlar dizi uzunluğu. Bir dizide tanımlı en yüksek öğesi daha yüksek bir sayı biri budur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
numVar = arrayObj.length   
```  
  
## <a name="parameters"></a>Parametreler  
 `numVar`  
 Gerekli. Herhangi bir sayı.  
  
 `arrayObj`  
 Gerekli. Tüm `Array` nesnesi.  
  
## <a name="remarks"></a>Açıklamalar  
 JavaScript'te diziler seyrek ve bir dizideki öğeler bitişik olması gerekmez. `length` Özelliği değildir dizisindeki öğelerin sayısı. Örneğin, aşağıdaki dizi tanımı'ndaki `my_array.length` 7, değil 2 içerir:  
  
```JavaScript  
var my_array = new Array( );  
my_array[0] = "Test";  
my_array[6] = "Another Test";  
```  
  
 Yaptığınız `length` özelliği önceki değerinden küçük, dizi kesilir ve herhangi bir öğe ile eşit veya daha yeni değeri büyük dizinler dizi `length` özelliği kaybolur.  
  
 Length özelliği önceki değerine büyük yaptığınız dizi genişletilir ve oluşturulan herhangi bir yeni öğe değerine sahip `undefined`.  
  
 Aşağıdaki örnek kullanımını göstermektedir `length` özelliği:  
  
```JavaScript  
var a;  
a = new Array(0,1,2,3,4);  
document.write(a.length);  
  
// Output  
// 5  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
> [!NOTE]
>  Internet Explorer 9 standartları modu ile başlayarak, bir dizi başlatma dahil Sondaki virgül farklı şekilde işlenir.