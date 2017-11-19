---
title: Beklenen &#39;] &#39; Normal ifadede (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.WebClient.Help.SCRIPT5019
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1ca2079a-44dd-479f-a1e3-e04a14d0739e
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4c59dcbeea91a1bc01e870d0a49fd22cace6562d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="expected-3939-in-regular-expression-javascript"></a>Beklenen &#39;] &#39; Normal ifade (JavaScript)
Normal ifade eşleştirmesi için karakter sınıfı oluşturmaya çalıştı, ancak sağ köşeli ayraç içermiyordu. Tek tek değişmez değer karakter birleşimleri köşeli ayraç içinde koyarak karakter sınıflara birleştirilebilecek. Bir karakter sınıfı içerdiği herhangi bir karakterle eşleşir. Örneğin, / [abc] / "a", "b", eşleşen herhangi bir harf ya da "c".  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Sağ köşeli ayraç normal ifadeye ekleyin.  
  
    > [!NOTE]
    >  Tek bir köşeli ayraç eşleştirmek isterseniz, ters eğik çizgi ile - kaçış \\[- tarafından bir özel karakter olarak yorumlanmaz şekilde [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)].  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Normal ifade nesnesi](../../javascript/reference/regular-expression-object-javascript.md)   
 [Normal ifade sözdizimini (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)