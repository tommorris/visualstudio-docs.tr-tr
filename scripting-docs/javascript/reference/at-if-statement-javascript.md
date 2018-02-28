---
title: '@ifDeyimi (JavaScript) | Microsoft Docs'
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
- '@if_JavaScriptKeyword'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- elif statement
- conditional statements, if
- if statement, @if
- else statement
- '@if statement'
ms.assetid: ff11b29d-c06a-4276-b11d-db73e2da98ac
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 87cfc157ab16b183ccf687fa221393be4ab74757
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="if-statement-javascript"></a>@ifDeyimi (JavaScript)
İfadenin değerine bağlı olarak bir deyim grubunu koşullu yürütür.  
  
> [!WARNING]
>  Koşullu derleme Internet Explorer 11 standartları modunda desteklenmez ve [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar. Koşullu derleme Internet Explorer 10 Standartları modunda ve önceki sürümlerde desteklenir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      @if (  
   condition1  
)  
   text1  
[@elif (  
   condition2  
)  
   text2]  
[@else  
   text3]  
@end   
```  
  
## <a name="parameters"></a>Parametreler  
 *Condition1, condition2*  
 İsteğe bağlı. Bir Boole değeri ifadeye dönüştürülebilen bir ifade.  
  
 `text1`  
 İsteğe bağlı. Varsa ayrıştırılacak metin `condition1` olan **doğru**.  
  
 `text2`  
 İsteğe bağlı. Varsa ayrıştırılacak metin `condition1` olan **false** ve `condition2` olan **doğru**.  
  
 `text3`  
 İsteğe bağlı. Her iki ayrıştırılacak metin `condition1` ve `condition2` olan **false**.  
  
## <a name="remarks"></a>Açıklamalar  
 Yazdığınız zaman bir `@if` deyimi, sahip olmadığınız ayrı bir satırda her yan tümcesi yerleştirilecek. Birden çok kullanabilirsiniz  **@elif**  yan tümceleri. Ancak, tüm  **@elif**  yan tümceleri gerekir önce gelen bir  **@else**  yan tümcesi.  
  
 `@if` Deyimi çeşitli seçenekler arasında hangi metnin metin çıktısı için kullanılması gerektiğini belirlemek için genellikle kullanılır.  
  
 ASP, ASP.NET sayfaları ya da komut satırı programları için yazılan betikler içinde koşullu derleme değişkenleri kullanmak yaygın değildir. Bu derleyicilerin yetenekleri başka yöntemler kullanarak belirlenebileceği içindir.  
  
 Bir Web sayfası için bir betik yazdığınızda, koşullu derleme kodunu her zaman açıklamalar içine ekleyin. Bu koşullu derlemeyi desteklemeyen ana bilgisayarların onu yok saymasını sağlar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir  **@if...@elif... @else... @end**  deyimi.  
  
```JavaScript  
/*@cc_on @*/  
/*@  
    document.write("JavaScript version: " + @_jscript_version + ".");  
    document.write("<br />");  
    @if (@_win32)  
        document.write("Running on a 32-bit version of Windows.");  
    @elif (@_win16)  
        document.write("Running on a 16-bit version of Windows.");  
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
 [@cc_onDeyimi](../../javascript/reference/at-cc-on-statement-javascript.md)   
 [@setDeyimi](../../javascript/reference/at-set-statement-javascript.md)