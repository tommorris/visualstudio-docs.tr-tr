---
title: "Debug.writeln işlevi (JavaScript) | Microsoft Docs"
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
- writeln
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- writeIn method
ms.assetid: c3aad0cd-0486-4161-9ba6-31d672da72af
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 848760e59632b05605de2d73615a2b025df363da
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="debugwriteln-function-javascript"></a>Debug.writeln İşlevi (JavaScript)
Dizeleri sonrasında bir yeni satır karakteri komut dosyası hata ayıklayıcısı gönderir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
Debug.writeln([str1 [, str2 [, ... [, strN]]]])  
```  
  
## <a name="parameters"></a>Parametreler  
 *str1, str2,..., strN*  
 İsteğe bağlı. İçin komut dosyası hata ayıklayıcısı göndermek için dizeleri.  
  
## <a name="remarks"></a>Açıklamalar  
 `Debug.writeln` İşlevi dizeleri, çalışma zamanında Microsoft komut dosyası hata ayıklayıcı komut penceresi için bir yeni satır karakteri arkasından gönderir. Komut dosyası değil kırılım, `Debug.writeln` işlevi etkisi yoktur.  
  
 `Debug.writeln` İşlevidir neredeyse aynı `Debug.write` işlevi. Tek fark `Debug.write` işlevi göndermez yeni satır karakteri dizeleri gönderdikten sonra.  
  
## <a name="example"></a>Örnek  
 Bu örnekte `Debug.writeln` Microsoft komut dosyası hata ayıklayıcı komut penceresi içinde değişkenin değerini görüntülemek için işlevi.  
  
> [!NOTE]
>  Bu örneği çalıştırmak için bir komut dosyası hata ayıklayıcısı yüklü olması gerekir ve komut dosyası hata ayıklama modunda çalıştırılması gerekir.  
>   
>  Internet Explorer 8 içeren [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] hata ayıklayıcı. Internet Explorer'ın önceki bir sürümünü kullanıyorsanız bkz [nasıl yapılır: etkinleştirme ve komut dosyası hata ayıklamayı Başlat Internet Explorer'dan](http://go.microsoft.com/fwlink/?LinkId=133801).  
  
```JavaScript  
var counter = 42;  
Debug.writeln("The value of counter is " + counter);  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [hata ayıklama nesnesi](../../javascript/reference/debug-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Debug.Write işlevi](../../javascript/reference/debug-write-function-javascript.md)