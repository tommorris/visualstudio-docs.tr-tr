---
title: "Açıklama deyimleri (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Comment_JavaScript
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- comments, ignoring
- comment statements
ms.assetid: b604824f-ac17-49d3-bcdb-2a893ab5fff8
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c270379725550e116928bbecd69e6be51c34992f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="comment-statements-javascript"></a>Açıklama Deyimleri (JavaScript)
Neden tarafından yoksayılacak açıklamaları [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] ayrıştırıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Single-line Comment:  
// comment   
```  
  
```  
Multiline Comment:  
/*  
comment  
*/  
```  
  
```  
Comments with conditional compilation:  
//@CondStatement   
  
/*@  
condStatement  
@*/  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `comment` Komut dosyanıza dahil etmek istediğiniz açıklama metnini değişkendir. `condStatement` Değişkendir koşullu derleme etkinleştirilmişse kullanılacak. Tek satırlı yorumlar kullandıysanız, aralarında boşluk olabilir "/ /" ve "@" karakter.  
  
 Bir komut dosyası bölümlerini tarafından okunur tutmak için açıklamaları kullanın [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] ayrıştırıcı. Bir programı açıklayıcı açıklamalar dahil etmek için açıklamaları kullanabilirsiniz.  
  
 Tek satırlı yorumlar kullandıysanız, ayrıştırıcı açıklama işaretçisi satırın sonuna arasındaki herhangi bir metni yoksayar. Çok satırlı yorumlar kullandıysanız, ayrıştırıcı başlangıcını ve bitişini işaretlerinin arasında herhangi bir metni yoksayar.  
  
 Açıklamalar, bu özelliği desteklemeyen tarayıcılar uyumluluğunu korurken koşullu derleme desteklemek için kullanılır. Bu tarayıcılar formlarda tek satırlı yorumlar veya çok satırlı yorumlar sırasıyla kabul eder.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek açıklamaları en yaygın kullanımları gösterilmektedir.  
  
```JavaScript  
/* This is a multiline comment that  
    can span as many lines as necessary.  */  
function myfunction(arg1, arg2){  
    var r;  
    // This is a single line comment.  
    r = arg1 + arg2  
    return(r);  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek koşullu derleme kullanmayı gösterir. Bu örnek yalnızca koşullu derleme tarafından etkinleştirilmişse, kullanılan özel yorum ayırıcıları kullanır `@cc_on` deyimi. Koşullu derleme desteği olmayan komut dosyası altyapıları yalnızca koşullu derlemenin desteklenmediğini söyleyen bir ileti görürler.  
  
```JavaScript  
/*@cc_on @*/  
/*@if (@_jscript_version >= 4)  
    alert("JavaScript version 4 or better");  
    @else @*/  
    alert("Conditional compilation not supported by this scripting engine.");  
/*@end @*/  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]