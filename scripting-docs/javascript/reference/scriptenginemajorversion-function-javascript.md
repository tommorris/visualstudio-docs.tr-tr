---
title: ScriptEngineMajorVersion işlevi (JavaScript) | Microsoft Docs
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
- ScriptEngineMajorVersion
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- ScriptEngineMajorVersion function
ms.assetid: 3e251bce-1e14-4cb5-b79f-53845d1920fd
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 815e6fb92744fc2145cae2cbaa6a5574c3ea3ecc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791414"
---
# <a name="scriptenginemajorversion-function-javascript"></a>ScriptEngineMajorVersion İşlevi (JavaScript)
Komut dosyası altyapısı ana sürüm numarası kullanımda alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
ScriptEngineMajorVersion()  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Dönüş değeri doğrudan kullanımda komut dosyası dili için dinamik bağlantı kitaplığı (DLL) içinde yer alan sürüm bilgilerini karşılık gelir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `ScriptEngineMajorVersion` işlevi:  
  
```JavaScript  
if (window.ScriptEngineMajorVersion) {  
    console.log(window.ScriptEngine());   
}  
  
Output: <current major version>  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ScriptEngine işlevi](../../javascript/reference/scriptengine-function-javascript.md)   
 [ScriptEngineBuildVersion işlevi](../../javascript/reference/scriptenginebuildversion-function-javascript.md)   
 [ScriptEngineMinorVersion işlevi](../../javascript/reference/scriptengineminorversion-function-javascript.md)