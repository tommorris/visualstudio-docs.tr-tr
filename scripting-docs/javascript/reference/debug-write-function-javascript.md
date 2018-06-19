---
title: Debug.Write işlevi (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- Write
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- write method [JavaScript]
ms.assetid: fd1cfbb3-46cb-47cc-896c-a70d457dd413
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 74aad7a01e0dc166f22173cf193b312e1fd4d804
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790400"
---
# <a name="debugwrite-function-javascript"></a>Debug.write İşlevi (JavaScript)
Dizeler için komut dosyası hata ayıklayıcısı gönderir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
Debug.write([str1 [, str2 [, ... [, strN]]]])  
```  
  
## <a name="parameters"></a>Parametreler  
 *str1, str2,..., strN*  
 İsteğe bağlı. İçin komut dosyası hata ayıklayıcısı göndermek için dizeleri.  
  
## <a name="remarks"></a>Açıklamalar  
 `Debug.write` İşlevi için bir komut dosyası hata ayıklayıcı komut penceresi dizeleri çalışma zamanında gönderir. Komut dosyası değil kırılım, `Debug.write` işlevi etkisi yoktur.  
  
 `Debug.write` İşlevidir neredeyse aynı `Debug.writeln` işlevi. Tek fark `Debug.writeln` işlev dizeleri gönderildikten sonra yeni satır karakteri gönderir.  
  
## <a name="example"></a>Örnek  
 Bu örnekte `Debug.write` komut dosyası hata ayıklayıcı komut penceresi içinde değişkenin değerini görüntülemek için işlevi.  
  
> [!NOTE]
>  Bu örneği çalıştırmak için bir komut dosyası hata ayıklayıcısı yüklü olması gerekir ve komut dosyası hata ayıklama modunda çalıştırılması gerekir.  
>   
>  Internet Explorer 8 içeren [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] hata ayıklayıcı. Internet Explorer'ın önceki bir sürümünü kullanıyorsanız bkz [nasıl yapılır: etkinleştirme ve komut dosyası hata ayıklamayı Başlat Internet Explorer'dan](http://go.microsoft.com/fwlink/?LinkId=133801).  
  
```JavaScript  
var counter = 42;  
Debug.write("The value of counter is " + counter);  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [hata ayıklama nesnesi](../../javascript/reference/debug-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Debug.writeln işlevi](../../javascript/reference/debug-writeln-function-javascript.md)