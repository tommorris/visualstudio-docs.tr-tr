---
title: Beklenen onaltılık basamak | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT1023
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 67a86df7-49f9-43cb-99c6-99b1a427827a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c9e29131c4ecf4f476a30da94ec67676d6bea347
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788759"
---
# <a name="expected-hexadecimal-digit"></a>Beklenen onaltılık basamak
Yanlış bir Unicode kaçış sırası oluşturuldu. Unicode kaçış sıraları tam olarak dört onaltılık basamak tarafından (daha fazla ve en az) ve ardından \u başlayın. Unicode onaltılık basamak yalnızca sayı 0-9, A-F pın'de büyük harf ve küçük harf a-f içerebilir. Aşağıdaki örnek, doğru biçimlendirilmiş bir Unicode kaçış sırası gösterir.  
  
```JavaScript  
z = "\u1A5F";  
```  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Unicode onaltılık basamak \u ile başlamak için yalnızca 0-9, A-F, küçük harf a-f pın'de büyük harf sayıları içeren emin olun; ve dört basamak gruplandırılır.  
  
    > [!NOTE]
    >  Bir dizede metin \u kullanın, sonra iki ters eğik çizgi - kullanmak istiyorsanız (\\\u)-bir ilk ters eğik çizgi kaçınmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri türleri](../../javascript/data-types-javascript.md)