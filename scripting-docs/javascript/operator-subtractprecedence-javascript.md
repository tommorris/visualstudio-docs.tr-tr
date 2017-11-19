---
title: "İşleç önceliği (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- operator precedence
- order of precedence
ms.assetid: cf3c510a-2214-4b47-b8fe-3521298efaab
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 82503a312a4a4996e3bd38f596eef3104af3f11b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="operator-precedence-javascript"></a>İşleç Önceliği (JavaScript)
İşleç öncelikleri bir ifade değerlendirilirken yapılan işlemlerin gerçekleştirilme sırasını anlatır. Daha yüksek önceliği olan işlemler düşük önceliği olanlardan önce gerçekleştirilir. Örneğin çarpma işlemi toplama işleminden önce yapılır.  
  
## <a name="includejavascriptjavascriptincludesjavascript-mdmd-operators"></a>[!INCLUDE[javascript](../javascript/includes/javascript-md.md)] İşleçler  
 Aşağıdaki tabloda [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] en yüksekten en düşük önceliğe doğru sıralı işleçler. Aynı önceliğe sahip işlemler soldan sağa değerlendirilir.  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|biçimindeki telefon numarasıdır. [ ] ( )|Alan erişimi, dizi dizini oluşturma, işlev çağrıları ve ifade gruplama|  
|++ -- - ~ ! Yeni typeof void Sil|Tekil işleçler, dönen veri türü, nesne oluşturma, tanımsız değerler|  
|* / %|Çarpma, bölme, modül bölme|  
|+ - +|Toplama, çıkartma, dize birleştirme|  
|<\< >> >>>|Bit kaydırma|  
|< \<= >> instanceof =|Küçüktür, küçük eşittir, büyüktür, büyük eşittir, instanceof|  
|== != === !==|Eşitlik, eşitsizlik, katı eşitlik ve katı eşitsizlik|  
|&|Bit düzeyinde AND|  
|^|Bit düzeyinde XOR|  
|&#124;|Bit düzeyinde OR|  
|&&|Mantıksal VE|  
|&#124;&#124;|Mantıksal VEYA|  
|?:|Koşullu|  
|= *OP*=|Atama, atama işlemi ile (+= gibi ve & =)|  
|,|Çoklu değerlendirme|  
  
 Parantezler işleç önceliği tarafından belirlenen değerlendirmenin sırasını değiştirmek için kullanılır. Bu, parantez içindeki bir ifadenin, değeri ifadenin geri kalanında kullanılmadan önce tamamen değerlendirildiği anlamına gelir.  
  
 Örneğin:  
  
```JavaScript  
var result = 78 * 96 + 3;  
document.write(result);  
document.write("<br/>");  
  
result = 78 * (9 + 3);  
document.write(result);  
  
// Output:  
// 7491  
// 936  
```  
  
 İlk ifadede üç işlev vardır: =, * ve +. İşleç önceliği kurallarına göre aşağıdaki sırayla değerlendirilir: \*, +, = (78 \* 96 = 7488, 7488 + 3 = 7491).  
  
 İkinci ifadede ( ) işleci önce değerlendirilir, bu sayede ek ifade çarpımdan önce değerlendirilir (9 + 3 = 12, 12 * 78 = 936).  
  
 Aşağıdaki örnek, çözümler ve işleçler çeşitli içeren bir deyim gösterir `true`.  
  
```JavaScript  
var num = 10;  
  
if(5 == num / 2 && (2 + 2 * num).toString() === "22") {  
    document.write(true);  
}  
    // Output:  
    // true  
```  
  
 İşleçler bu sırayla değerlendirilir: gruplandırma () *, + (içinde gruplandırma), "." işlevi için () işlev için /, ==, ===, ve & &.