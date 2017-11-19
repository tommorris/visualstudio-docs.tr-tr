---
title: "String.RAW işlevi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: b1038b73-3944-4645-b075-3a674b313762
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 53df2bf0e455da8b1ccc6de3cbf3f4e3ebee4c09
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="stringraw-function-javascript"></a>String.raw İşlevi (JavaScript)
Şablon dizesini ham dize biçiminde döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
String.raw`templateStr`;  
String.raw(obj, ...substitutions);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `templateStr`  
 Gerekli. Şablon dizesi.  
  
 `obj`  
 Gerekli. Nesne değişmez değer gösterimi kullanılarak belirtilen doğru biçimlendirilmiş bir nesne {ham: 'value'}.  
  
 `...substitutions`  
 İsteğe bağlı. Bir dizi (bir [rest parametresi](../../javascript/functions-javascript.md)) oluşan bir veya daha fazla değiştirme değerleri.  
  
## <a name="remarks"></a>Açıklamalar  
 `String.raw` İşlevi ile kullanılmak üzere tasarlanmıştır [şablonu dizeleri](../../javascript/advanced/template-strings-javascript.md). Ham dizesini herhangi bir kaçış karakterleri ve dizesinde mevcut ters eğik çizgi içerir.  
  
 Bir hata durumunda atılır `obj` doğru biçimlendirilmiş bir nesne değil.  
  
## <a name="example"></a>Örnek  
  
```  
function log(arg) {  
    if(console && console.log) {  
        console.log(arg);  
    }  
};  
  
var name = "bob";  
  
log(`hello \t${name}`);  
log(String.raw`hello \t${name}`);  
// The following usage for String.raw is supported but  
// is not typical.  
log(String.raw({ raw: 'fred'}, 'F', 'R', 'E'));  
  
// Output:  
// hello   bob  
// hello \tbob  
// fFrReEd   
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]