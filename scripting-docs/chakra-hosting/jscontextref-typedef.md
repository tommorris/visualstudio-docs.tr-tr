---
title: Jscontextref tür | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 8586bfcc-bb24-430d-a6f2-1a3b3e34ec2e
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ec1300717b59c3b901665b39ca0102988e83e853
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788219"
---
# <a name="jscontextref-typedef"></a>JsContextRef Tür Tanımı
Bir betik içeriğine başvuru.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef JsRef JsContextRef;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Her bir betik bağlamı, diğer betik bağlamlarındaki genel nesnenden farklı olan kendi genel nesnesini içerir.  
  
 Barındırma API'leri kullanılarak ayarlanabilir bir "etkin" komut dosyası bağlamı gerektiren birçok Chakra `JsSetCurrentContext`. Ayarlanmak üzere geçerli bir bağlam gerektiren Chakra barındırma API'leri belgelerinde bunu açıkça belirtir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)