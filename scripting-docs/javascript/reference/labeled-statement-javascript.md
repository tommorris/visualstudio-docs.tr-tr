---
title: Deyimi (JavaScript) etiketli | Microsoft Docs
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
- labeled_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- continue statement
- labeled statement
- identifiers, statements
ms.assetid: 019f898e-9e27-4be4-a22f-c5927c7fcae2
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bd72b15d3fc9083ca127a48981c0cd0a7ee56b6c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="labeled-statement-javascript"></a>Etiketli Deyim (JavaScript)
Bir deyim için bir tanımlayıcı sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      label :  
   statements   
```  
  
## <a name="parameters"></a>Parametreler  
 *Etiket*  
 Gerekli. Etiketli deyim başvururken kullanılan benzersiz bir tanımlayıcı.  
  
 `statements`  
 İsteğe bağlı. İle ilişkili bir veya daha fazla deyimleri *etiket*.  
  
## <a name="remarks"></a>Açıklamalar  
 Etiketleri tarafından kullanılan **sonu** ve **devam** ifadesine belirtmek için deyimleri **sonu** ve **devam** uygulayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodda, **devam** deyimi başvurduğu **için** öncesinde döngü `Inner:` deyimi. Zaman `j` 24'ün, **devam** deyimi neden **için** döngü sonraki yinelemeye gidin. 23 ve 25 ile 30 arasında 21 sayıları, her satırda yazdırın.  
  
```JavaScript  
Outer:  
for (i = 1; i <= 10; i++) {  
   document.write ("<br />");  
   document.write ("i: " + i);  
   document.write (" j: ");  
  
Inner:  
   for (j = 21; j <= 30; j++) {  
      if (j == 24)  
          {  
          continue Inner;  
      }  
      document.write (j + " ");  
  }  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [break deyimi](../../javascript/reference/break-statement-javascript.md)   
 [continue deyimi](../../javascript/reference/continue-statement-javascript.md)