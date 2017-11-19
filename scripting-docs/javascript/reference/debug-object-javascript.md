---
title: "Hata ayıklama nesnesi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: debug
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Debug object
- Debug object, about Debug object
ms.assetid: 42a367ec-beb1-4e59-8342-34c326eca042
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6286e5db853daa97e43f36a1467abe90cbced5c8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="debug-object-javascript"></a>Hata Ayıklama Nesnesi (JavaScript)
Bir hata ayıklayıcısı çıkış gönderir iç global nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.function  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklama nesnesi örneği değil. Çağırarak tüm özellikleri ve yöntemleri erişebilirsiniz `function`.  
  
 Internet Explorer hata ayıklamak için farklı yolu vardır ve [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar. İçinde [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar, `write` ve `writeln` işlevlerini `Debug` nesne görünen dizeler Visual Studio'da **çıkış** çalışma zamanında penceresi. Hata ayıklama hakkında daha fazla bilgi için [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamaları bkz [Windows Evrensel uygulamaları hata ayıklama Visual Studio'da](/visualstudio/debugger/debugging-windows-store-and-windows-universal-apps.md).  
  
 Internet Explorer betikleri hata ayıklamak için bir komut dosyası hata ayıklayıcısı yüklü olması gerekir ve komut dosyası hata ayıklama modunda çalıştırılması gerekir. Internet Explorer 8 ve sonraki sürümleri dahil [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] hata ayıklayıcı. Internet Explorer'ın önceki bir sürümünü kullanıyorsanız bkz [nasıl yapılır: etkinleştirme ve komut dosyası hata ayıklamayı Başlat Internet Explorer'dan](http://go.microsoft.com/fwlink/?LinkId=133801).  
  
 Komut dosyası değil kırılım, işlevleri bir etkisi yoktur.  
  
## <a name="example"></a>Örnek  
 Bu örnekte `write` değişkenin değerini görüntülemek için işlevi.  
  
```JavaScript  
var counter = 42;  
Debug.write("The value of counter is " + counter);  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="constants"></a>Sabitler  
 [Debug sabitleri](../../javascript/reference/debug-constants.md)  
  
## <a name="properties"></a>Özellikler  
 [Debug.debuggerEnabled özelliği](../../javascript/reference/debug-debuggerenabled-property.md) &#124; [Debug.setNonUserCodeExceptions özelliği](../../javascript/reference/debug-setnonusercodeexceptions-property.md)  
  
## <a name="functions"></a>İşlevler  
 [Debug.msTraceAsyncCallbackStarting işlevi](../../javascript/reference/debug-mstraceasynccallbackstarting-function.md) &#124; [Debug.msTraceAsyncCallbackCompleted işlevi](../../javascript/reference/debug-mstraceasynccallbackcompleted-function.md) &#124; [Debug.msTraceAsyncOperationCompleted işlevi](../../javascript/reference/debug-mstraceasyncoperationcompleted-function.md) &#124; [Debug.msTraceAsyncOperationStarting işlevi](../../javascript/reference/debug-mstraceasyncoperationstarting-function.md) &#124; [Debug.msUpdateAsyncCallbackRelation işlevi](../../javascript/reference/debug-msupdateasynccallbackrelation-function.md) &#124; [Debug.write işlevi](../../javascript/reference/debug-write-function-javascript.md) &#124; [Debug.writeln işlevi](../../javascript/reference/debug-writeln-function-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Debugger deyimi](../../javascript/reference/debugger-statement-javascript.md)