---
title: Hata nesnesi (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Error
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: Error object
ms.assetid: 0b27d6ec-3997-4e91-a6c0-5afbaf494db7
caps.latest.revision: "25"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: efc03f13a501a1a13a2e7f3eea000b406559f30b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="error-object-javascript"></a>Hata Nesnesi (JavaScript)
Hatalar hakkında bilgi içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      errorObj = new Error()  
errorObj = new Error([number])  
errorObj = new Error([number[, description]])  
```  
  
## <a name="parameters"></a>Parametreler  
 `errorObj`  
 Gerekli. Değişken adına `Error` nesne atanır. Hata kullanarak oluşturduğunuz değişken ataması atlanır bir `throw` deyimi.  
  
 `number`  
 İsteğe bağlı. Bir hataya atanan sayısal değer. Atlanırsa sıfır.  
  
 `description`  
 İsteğe bağlı. Bir hatayı açıklayan kısa dize. Atlanırsa, dizeyi boşaltın.  
  
## <a name="remarks"></a>Açıklamalar  
 Her bir çalışma zamanı hatası oluşur, örneği `Error` nesnesi hata açıklamak için oluşturulur. Bu örneği hatanın açıklamasını içeren iki iç özelliklerine sahiptir (`description` özelliği) ve hata sayısı (`number` özelliği). Daha fazla bilgi için bkz: [JavaScript çalışma zamanı hataları](../../javascript/reference/javascript-run-time-errors.md).  
  
 Hata numarası, 32 bit bir değerdir. Üst 16 bit sözcük tesis kodu, alt sözcük ise gerçek hata kodudur.  
  
 `Error`nesneleri aynı zamanda açıkça oluşturulabilir, yukarıda gösterilen veya kullanılarak oluşturulan sözdizimini kullanarak `throw` deyimi. Her iki durumda da yeteneğini genişletmek için seçtiğiniz tüm özelliklerini ekleyebilirsiniz `Error` nesnesi.  
  
 Genellikle, oluşturulan yerel değişken bir **try... catch** deyimi başvuruyor örtük olarak oluşturulmuş `Error` nesnesi. Sonuç olarak, hata numarası ve açıklamasını istediğiniz şekilde kullanabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `Error` nesnesi.  
  
```  
function checkInput(x) {  
    try  
    {  
        if (isNaN(parseInt(x))) {  
            throw new Error("Input is not a number.");  
        }  
    }  
    catch(e)  
    {  
        document.write(e.description);  
    }  
}  
  
checkInput("not a number");  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek örtük olarak oluşturulmuş kullanımını göstermektedir `Error` nesnesi.  
  
```JavaScript  
try  
   {  
   // Cause an error.  
   x = y;  
   }  
catch(e)  
   {  
      document.write(e);  
      document.write ("<br />");  
  
      document.write ("Number: ");  
      document.write (e.number & 0xFFFF);  
      document.write ("<br />");  
  
      document.write ("Facility Code: ");  
      document.write(e.number>>16 & 0x1FFF);  
      document.write ("<br />");  
  
      document.write ("Description: ");  
      document.write (e.description);  
   }  
  
// Output:  
// ReferenceError: 'y' is undefined  
// Number: 5009  
// Facility Code: 10  
// Description: 'y' is undefined  
  
```  
  
## <a name="methods"></a>Yöntemler  
 [toString yöntemi (hata)](../../javascript/reference/tostring-method-error.md) &#124; [valueOf yöntemi (tarih)](../../javascript/reference/valueof-method-date.md)  
  
## <a name="properties"></a>Özellikler  
 [constructor özelliği (hata)](../../javascript/reference/constructor-property-error.md) &#124; [description özelliği](../../javascript/reference/description-property-error-javascript.md) &#124; [message özelliği](../../javascript/reference/message-property-error-javascript.md) &#124; [name özelliği](../../javascript/reference/name-property-error-javascript.md) &#124; [number özelliği](../../javascript/reference/number-property-error-javascript.md) &#124; [prototype özelliği (hata)](../../javascript/reference/prototype-property-error.md) &#124; [stack özelliği (hata)](../../javascript/reference/stack-property-error-javascript.md) &#124; [stackTraceLimit özelliği (hata)](../../javascript/reference/stacktracelimit-property-error-javascript.md)  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [New işleci](../../javascript/reference/new-operator-decrementjavascript.md)   
 [throw deyimi](../../javascript/reference/throw-statement-javascript.md)   
 [try... catch... finally deyimi](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)   
 [var deyimi](../../javascript/reference/var-statement-javascript.md)   
 [Hilo JavaScript örnek uygulama (Windows mağazası)](http://hilojs.codeplex.com/SourceControl/latest)