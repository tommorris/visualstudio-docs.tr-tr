---
title: 'Hata: Web hizmetlerinde hata ayıklama sırasında zaman aşımı | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
- XML Web services, timeout while debugging
ms.assetid: 4b7df112-788a-4429-9a0c-4c6dac4fb609
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dee3017114c645c5bc3c2001e0cb2cafda48ef53
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694934"
---
# <a name="error-timeout-while-debugging-web-services"></a>Hata: Web Hizmetlerinde Hata Ayıklarken Zaman Aşımı
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata: zaman aşımı sırasında hata ayıklama Web Hizmetleri](https://docs.microsoft.com/visualstudio/debugger/error-timeout-while-debugging-web-services).  
  
Çağrıldığı koddan bir XML Web hizmeti adımladığınızda, hata ayıklama devam edemiyor emin olmasına çağrı bazen sonuç zaman aşımı olabilir. Bunun gibi bir hata iletisi görebilirsiniz.  
  
```  
An unhandled exception of type 'System.Net.WebException' occurred in   
system.Web.services.dll  
Additional information: The operation has timed-out.  
```  
  
## <a name="solution"></a>Çözüm  
 Bu sorunu önlemek için XML Web hizmeti çağrısı için zaman aşımı değeri sonsuz olarak, bu örnekte gösterilen şekilde ayarlayın:  
  
```  
Service1 obj = new Service1();  
obj.TimeOut = -1; // infinite time out.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Web uygulamalarında hata ayıklama: Hatalar ve sorun giderme](../debugger/debugging-web-applications-errors-and-troubleshooting.md)



