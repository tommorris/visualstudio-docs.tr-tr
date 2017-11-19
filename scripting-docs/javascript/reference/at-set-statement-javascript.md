---
title: '@setDeyimi (JavaScript) | Microsoft Docs'
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '@set_JavaScriptKeyword'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '@set statement'
- conditional compilation, variables
ms.assetid: 36f15926-3e69-422d-82a2-d186dc088203
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 10f74a1d57a61d78897b660812a6fd8078244b6b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="set-statement-javascript"></a>@setDeyimi (JavaScript)
Koşullu derleme deyimleriyle kullanılan değişkenler oluşturur.  
  
> [!WARNING]
>  Koşullu derleme Internet Explorer 11 standartları modunda desteklenmez ve [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar. Koşullu derleme Internet Explorer 10 Standartları modunda ve önceki sürümlerde desteklenir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
@set @varname = term   
```  
  
## <a name="parameters"></a>Parametreler  
 *varName*  
 Gerekli. Geçerli [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] değişken adı. Her zaman başında bir "@" karakteri olmalıdır.  
  
 `term`  
 Gerekli. Sonrasında bir sabit, koşullu derleme değişkeni, ya da parantezli ifade bulunan sıfır ya da daha fazla tekli işleç.  
  
## <a name="remarks"></a>Açıklamalar  
 Koşullu derleme için sayısal ve Boolean değişkenler desteklenir. Dizeler desteklenmez. Kullanılarak oluşturulan değişkenleri `@set` koşullu derleme deyimlerinde genellikle kullanılır, ancak herhangi bir yerde kullanılabilir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] kodu.  
  
 Değişken tanımlama örnekleri aşağıdaki gibidir:  
  
```JavaScript  
  
      @set @myvar1 = 12  
  
@set @myvar2 = (@myvar1 * 20)  
  
@set @myvar3 = @_jscript_version  
```  
  
 Aşağıdaki işleçler parantezli ifadelerde desteklenir:  
  
-   `! ~`  
  
-   `* / %`  
  
-   `+ -`  
  
-   `<< >> >>>`  
  
-   `< <= > >=`  
  
-   `== != === !==`  
  
-   `& ^ |`  
  
-   `&& | |`  
  
 Tanımlanmış önce bir değişken kullanılırsa, değeri olduğu `NaN`. `NaN`kullanmak için denetlenebilir `@if` deyimi:  
  
```JavaScript  
@if (@newVar != @newVar)  
   ...  
```  
  
 Bu çalışır çünkü `NaN` tek değer kendisine eşit değil.  
  
## <a name="requirements"></a>Gereksinimler  
 Internet Explorer'ın ancak değil, tüm sürümlerinde desteklenen [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koşullu derleme](../../javascript/advanced/conditional-compilation-javascript.md)   
 [Koşullu derleme değişkenleri](../../javascript/advanced/conditional-compilation-variables-javascript.md)   
 [@cc_onDeyimi](../../javascript/reference/at-cc-on-statement-javascript.md)   
 [@ifDeyimi](../../javascript/reference/at-if-statement-javascript.md)