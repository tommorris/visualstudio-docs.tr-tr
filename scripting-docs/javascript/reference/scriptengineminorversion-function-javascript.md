---
title: "ScriptEngineMinorVersion işlevi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: ScriptEngineMinorVersion
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: ScriptEngineMinorVersion function
ms.assetid: caa506a5-e61d-4b2a-8b83-83d56a2f26cd
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b1be01c0ee10cac1c68d4750455151032a59a8e6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="scriptengineminorversion-function-javascript"></a>ScriptEngineMinorVersion İşlevi (JavaScript)
Komut dosyası altyapısı alt sürüm numarasını kullanımda alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
ScriptEngineMinorVersion()  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Dönüş değeri doğrudan kullanımda komut dosyası dili için dinamik bağlantı kitaplığı (DLL) içinde yer alan sürüm bilgilerini karşılık gelir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `ScriptEngineMinorVersion` işlevi.  
  
```JavaScript  
if (window.ScriptEngineMinorVersion) {  
    console.log(window.ScriptEngineMinorVersion());  
}  
  
//Output: <current minor version>  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ScriptEngine işlevi](../../javascript/reference/scriptengine-function-javascript.md)   
 [ScriptEngineBuildVersion işlevi](../../javascript/reference/scriptenginebuildversion-function-javascript.md)   
 [ScriptEngineMajorVersion işlevi](../../javascript/reference/scriptenginemajorversion-function-javascript.md)