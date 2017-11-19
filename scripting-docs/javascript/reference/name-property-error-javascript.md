---
title: "name özelliği (hata) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: name
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Name property
- name property, error name
ms.assetid: 94df2d6b-f1a1-4931-a956-0a930cb87f76
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1a12157b4c467499fab23f7c4cb1be91e9ac5440
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="name-property-error-javascript"></a>name Özelliği (Hata) (JavaScript)
Bir hata adını döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
errorObj.  
name  
  
```  
  
## <a name="parameters"></a>Parametreler  
 `errorObj`  
 Gerekli. Örneğini `Error` nesnesi.  
  
## <a name="remarks"></a>Açıklamalar  
 **Adı** özelliği hata adı veya özel durum türünü döndürür. Bir çalışma zamanı hatası oluştuğunda, name özelliği aşağıdaki yerel özel durum türleri birine ayarlayın:  
  
|Özel durum türü|Açıklama|  
|--------------------|-------------|  
|ConversionError|Nesneyi bir şey için bunu dönüştürülemiyor dönüştürme girişimi olduğunda bu hata oluşur.|  
|RangeError|Bu hata, bir işlev, izin verilen aralığın aştı bir bağımsız değişkeni ile sağlanan oluşur. Örneğin, oluşturmak denerseniz, bu hata oluşur. bir `Array` nesne geçerli bir pozitif tamsayı olmayan uzunluğa sahip.|  
|ReferenceError|Geçersiz bir başvuru algılandı. Bu hata oluşur. Beklenen bir başvuru ise bu hata, örneğin, oluşacaktır `null`.|  
|RegExpError|Normal ifadeyle uyumlu bir derleme hatası oluştuğunda, bu hata oluşur. Bununla birlikte, normal ifade derlenmiş sonra bu hata gerçekleşemez. Normal bir ifade sözdizimi geçersiz ya da dışında bayrakları bir desenle bildirildiğinde Bu örnek, örneğin, meydana gelir **ı**, **g**, veya **m**, veya içeriyorsa birden çok kez aynı bayrak.|  
|SyntaxError|Kaynak metni ayrıştırılır ve bu kaynak metni doğru sözdizimi izlemez bu hata oluşur. Bu hata, örneğin, oluşacaktır `eval` işlevi, geçerli program metin olmayan bir bağımsız değişken çağrılır.|  
|TypeError|Gerçek tür işleneni, beklenen türle eşleşmiyor olduğunda bu hata oluşur. Bu hata oluştuğunda, bir nesne değil ya da aramayı desteklemiyor şeye yapılan bir işlev çağrısı örneğidir.|  
|URIError|Bir geçersiz Tekdüzen Kaynak göstergesi'nı (URI) algıladığında, bu hata oluşur. Örneğin, bu hata geçersiz bir karakter dizesi olan içinde kodlanmış veya kodunu çözdü bulunduğunda oluşur.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir TypeError özel durum oluşturulmasına neden olur ve hata ve kendi ileti adını görüntüler.  
  
```JavaScript  
try  
{  
    var x = y;  
}  
catch(e)  
{  
    document.write ("Error Message: " + e.message);  
    document.write ("<br />");  
    document.write ("Error Code: ");  
    document.write (e.number & 0xFFFF)  
    document.write ("<br />");  
    document.write ("Error Name: " + e.name);  
}  
```  
  
## <a name="example"></a>Örnek  
 Bu kod çıkışı aşağıdaki gibidir.  
  
```JavaScript  
Error Message: 'y' is undefined  
Error Code: 5009  
Error Name: TypeError  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Uygulandığı öğe**: [hata nesnesi](../../javascript/reference/error-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Description özelliği (hata)](../../javascript/reference/description-property-error-javascript.md)   
 [message özelliği (hata)](../../javascript/reference/message-property-error-javascript.md)   
 [Number özelliği (hata)](../../javascript/reference/number-property-error-javascript.md)