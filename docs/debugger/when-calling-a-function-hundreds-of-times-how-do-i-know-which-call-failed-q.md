---
title: "İşlevi Yüzlerce Kere Çağırırken Hangi Çağrının Başarısız Olduğunu Nasıl Bilebilirim? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.functions
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- conditional breakpoints
- errors [debugger], function calls
- breakpoints, troubleshooting
- errors [debugger], finding which function call failed
- failures
- location breakpoint call failures
- errors [Visual Studio], function calls
- hit counts
- function calls, failure
- functions [debugger]
- Skip Count
ms.assetid: 66cfac86-f5be-4d3a-9329-d44cd74bc586
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f36e482f7c5028f5a6e81d8fba21bb78763cb01a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="when-calling-a-function-hundreds-of-times-how-do-i-know-which-call-failed"></a>İşlevi Yüzlerce Kere Çağırırken Hangi Çağrının Başarısız Olduğunu Nasıl Bilebilirim?
## <a name="problem-description"></a>Sorun açıklaması  
 Kendi programımı belirli bir işlevi çağrısı başarısız `CnvtV`. Bu başarısız olmadan önce programı büyük olasılıkla bu işlevi birkaç yüzlerce kez çağırır. I üzerinde bir konum kesme noktası ayarlarsanız `CnvtV`, programı durdurur, işlevi her çağrıda ve ı, istemiyorsanız. Koşullu kesme noktası ayarlama edilemez şekilde hangi koşullar çağrının başarısız olmasına neden bilebilirim değil. Ne yapabilirim?  
  
## <a name="solution"></a>Çözüm  
 İşlev üzerinde bir kesme noktası ayarlayabilirsiniz **isabet sayısı** , hiçbir zaman ulaşılacak kadar yüksek bir değere alan. Bu durumda, işlevi düşünüyorsanız çünkü `CnvtV` birkaç adlı yüzlerce kez, ayarlayabilirsiniz **isabet sayısı** 1000 veya daha fazla. Ardından programını çalıştırın ve çağrısı başarısız bekleyin. Bu başarısız olduğunda, kesme noktaları penceresini açın ve kesme noktaları listesine bakın. Açık ayarlayın kesme noktası `CnvtV` görünür, ardından isabet sayısı ve kalan yineleme sayısı:  
  
```  
CnvtV(int) (no condition) when hit count is equal to 1000 (currently 101)  
```  
  
 İşlev 101st çağrıda başarısız oldu biliyorsunuz. Kesme noktası isabet sayısı 101 ile sıfırlamak ve programı yeniden çalıştırın, program çağrısı durakları `CnvtV` , başarısız olmasına neden.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel kod hata ayıklaması SSS](../debugger/debugging-native-code-faqs.md)   
 [Kesme noktalarını ayarlama](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583)   
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)