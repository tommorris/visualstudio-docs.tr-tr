---
title: Diziler (JavaScript) kullanarak | Microsoft Docs
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
helpviewer_keywords:
- arrays [JavaScript]
- arrays [JavaScript], objects
ms.assetid: 785c5acd-b8b3-4152-af9a-dd42ecdd75ba
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4c5218a8353a796128d8b672ecc781665c6bde20
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788789"
---
# <a name="using-arrays-javascript"></a>Dizileri Kullanma (JavaScript)
İçindeki diziler [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] olan *seyrek*. Diğer bir deyişle, bir dizi numaralı 0, 1 ve 2 olan üç öğe varsa, öğeleri 49 3 hakkında endişelenmeden öğesi 50 oluşturabilirsiniz. Dizi otomatik uzunluk değişkeni varsa (bkz [iç nesneler](../../javascript/intrinsic-objects-javascript.md) otomatik dizi uzunluğu izleme bir açıklama için), uzunluk değişkeni 51 yerine 4 ayarlanır. Öğeleri numaralandırmayı hiçbir boşluk olduğu dizileri oluşturabilirsiniz, ancak bunu yapmak için gerekli değildir.  
  
 İçinde [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)], nesneler ve diziler birbirlerine neredeyse aynı. Dizi olmayan nesneleri otomatik length özelliği yoktur ve diziler özellikleri ve yöntemleri bir nesnenin olmayan iki temel farklılıklar şunlardır.  
  
## <a name="addressing-arrays"></a>Diziler adresleme  
 Aşağıdaki örnekte gösterildiği gibi köşeli ayraç ([]) kullanarak dizileri adres. Köşeli sayısal bir değer veya bir tam sayıya veren ifade kapatın.  
  
```JavaScript  
var entryNum = 5;  
  
sample = new Array();  
  
sample[1] = "Maple Street";  
sample[entryNum] = 25;  
  
document.write (sample[1]);  
document.write (" ");  
document.write (sample[entryNum]);  
  
// Output: Maple Street 25  
  
```  
  
## <a name="objects-as-associative-arrays"></a>Nesneler olarak ilişkilendirilebilir diziler  
 Nokta işleci genellikle kullanması "." bir nesnenin özelliklerine erişmek için. Örneğin,  
  
```JavaScript  
myObject.aProperty  
```  
  
 Bu durumda özellik adı bir tanımlayıcıdır. Bir nesnenin özelliklerini dizin işleci ([]) kullanarak da erişebilirsiniz. Bu durumda, nesne değerlendirme bir *ilişkilendirilebilir dizi* , veri değerleri dizeler ile ilişkilendirilmiş. Örneğin,  
  
```JavaScript  
myObject["aProperty"] // Same as above.  
```  
  
 Dizin işleci daha sık dizi öğelere erişme ile ilişkilidir. Nesneler ile kullanıldığında, özellik adı temsil eden bir dize dizinidir.  
  
 Nesne özellikleri erişmenin iki yolu arasındaki önemli farklılıklar dikkat edin.  
  
1.  Bir tanımlayıcı (nokta (.) sözdizimi) gibi veri değiştirilemiyor gibi bir özellik adı kabul edilir.  
  
2.  (Köşeli parantez ([]) sözdizimi) dizin verileri gibi yönetilebilir gibi bir özellik adı kabul edilir.  
  
 Özellik adlarının çalışma zamanı (örneğin, kullanıcı girişini temel alarak nesneleri oluşturulurken) kadar olacak bilmiyorsanız, bu fark yararlı olur. Tüm özellikleri ilişkilendirilebilir dizisinden ayıklamak için kullanmanız gerekir `for...in` döngü.