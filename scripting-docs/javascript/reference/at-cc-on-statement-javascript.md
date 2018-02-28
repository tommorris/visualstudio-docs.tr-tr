---
title: '@cc_onDeyimi (JavaScript) | Microsoft Docs'
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
- '@cc_on_JavaScriptKeyword'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- conditional compilation, activating
- '@cc_on statement'
- '@set statement'
- '@if statement'
ms.assetid: fdeda7ee-b9f4-4e52-8aa2-21c90c02a332
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d7e993d5bc8302931a5722495da70612e79f7dfd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="ccon-statement-javascript"></a>@cc_onDeyimi (JavaScript)
Bir betikte açıklamalar içinde koşullu derleme desteğini etkinleştirir.  
  
> [!WARNING]
>  Koşullu derleme Internet Explorer 11 standartları modunda desteklenmez ve [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar. Koşullu derleme Internet Explorer 10 Standartları modunda ve önceki sürümlerde desteklenir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
@cc_on   
```  
  
## <a name="remarks"></a>Açıklamalar  
 `@cc_on` İfadesi bir komut dosyası açıklamaları içinde koşullu derleme etkinleştirir.  
  
 ASP ya da ASP.NET sayfaları ya da komut satırı programları için yazılan betikler içinde koşullu derleme değişkenleri kullanmak yaygın değildir çünkü derleyicilerin yetenekleri başka yöntemler kullanarak belirlenebilir.  
  
 Bir Web sayfası için bir betik yazdığınızda, koşullu derleme kodunu her zaman açıklamalar içine koyun. Bu koşullu derlemeyi desteklemeyen ana bilgisayarların onu yok saymasını sağlar.  
  
 Kullanmanız önemle tavsiye edilir `@cc_on` deyiminde yorum, böylece koşullu derleme desteklemeyen tarayıcılar, komut dosyası geçerli sözdizimi olarak kabul eder:  
  
 Bir `@if` veya `@set` deyimi bir yorum dışında ayrıca koşullu derleme etkinleştirir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `@cc_on` deyimi.  
  
```JavaScript  
/*@cc_on @*/  
/*@  
    document.write("JavaScript version: " + @_jscript_version + ".");  
    document.write("<br />");  
    @if (@_win32)  
        document.write("Running on the 32-bit version of Windows.");  
    @elif (@_win16)  
        document.write("Running on the 16-bit version of Windows.");  
    @else  
        document.write("Running on a different operating system.");  
    @end  
@*/  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Internet Explorer'ın ancak değil, tüm sürümlerinde desteklenen [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koşullu derleme](../../javascript/advanced/conditional-compilation-javascript.md)   
 [Koşullu derleme değişkenleri](../../javascript/advanced/conditional-compilation-variables-javascript.md)   
 [@ifDeyimi](../../javascript/reference/at-if-statement-javascript.md)   
 [@setDeyimi](../../javascript/reference/at-set-statement-javascript.md)