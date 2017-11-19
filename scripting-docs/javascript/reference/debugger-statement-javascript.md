---
title: "hata ayıklayıcı deyimi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: debugger_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: debugger statement
ms.assetid: c6d2e193-c1f7-4fb3-8a4e-cc9823174ae4
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9e64e860cebd065f357857484e932b4aea3f05ea
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="debugger-statement-javascript"></a>debugger Deyimi (JavaScript)
Yürütme askıya alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
debugger  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Yerleştireceğiniz `debugger` yürütme askıya almak için herhangi bir yere yordamları deyimlerinde. Kullanarak `debugger` deyimi kodda kesme noktası ayarlama benzer.  
  
 `debugger` Deyimi yürütme askıya alır, ancak değil tüm dosyaları kapatın veya herhangi bir değişkeni temizleyin.  
  
> [!NOTE]
>  `debugger` Deyimi, komut dosyası hata ayıklaması sürece hiçbir etkisi vardır.  
  
## <a name="example"></a>Örnek  
 Bu örnekte `debugger` yürütme her bir yineleme için askıya almak için deyimi `for` döngü.  
  
> [!NOTE]
>  Bu örneği çalıştırmak için bir komut dosyası hata ayıklayıcısı yüklü olması gerekir ve komut dosyası hata ayıklama modunda çalıştırılması gerekir.  
>   
>  Internet Explorer 8 içeren [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] hata ayıklayıcı. Internet Explorer'ın önceki bir sürümünü kullanıyorsanız bkz [nasıl yapılır: etkinleştirme ve komut dosyası hata ayıklamayı Başlat Internet Explorer'dan](http://go.microsoft.com/fwlink/?LinkId=133801).  
  
```JavaScript  
for(i = 1; i<5; i++) {  
   // Print i to the Output window.  
   Debug.write("loop index is " + i);  
   // Wait for user to resume.  
   debugger  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JavaScript deyimleri](../../javascript/reference/javascript-statements.md)   
 [Koşullu derleme](../../javascript/advanced/conditional-compilation-javascript.md)