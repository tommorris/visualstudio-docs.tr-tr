---
title: Atama kancaları ve C çalışma zamanı bellek ayırmaları | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.hooks
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging [C++], hook functions
- memory allocation, troubleshooting allocation hooks
- allocation hooks
- hooks, allocation
ms.assetid: cc34ee96-3d91-41bd-a019-aa3759139e7e
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f3dbb9f2640d3da71566b8c8839b413943927af2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685813"
---
# <a name="allocation-hooks-and-c-run-time-memory-allocations"></a>Atama Kancaları ve C Çalışma Zamanı Bellek Ayırmaları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ayırma kancaları ve C çalışma zamanı bellek ayırmaları](https://docs.microsoft.com/visualstudio/debugger/allocation-hooks-and-c-run-time-memory-allocations).  
  
Atama kanca işlevleri çok önemli bir kısıtlama bunlar açıkça yoksayması gereken olduğu `_CRT_BLOCK` bloklar (C çalışma zamanı kitaplığı işlevleri tarafından dahili olarak yapılan bellek ayırmaları) tahsis C çalışma zamanı kitaplık işlevleri çağrıları'na yaparsanız iç bellek. `_CRT_BLOCK` Blokları, ayrılan başında aşağıdaki kanca işlevi gibi kod ekleyerek göz ardı:  
  
```  
if ( nBlockUse == _CRT_BLOCK )  
    return( TRUE );  
```  
  
 Atama kanca değil yoksayarsanız `_CRT_BLOCK` , içindeki kanca adlı tüm C çalışma zamanı kitaplığı işlevi sonsuz bir döngünün program yakalayabilir sonra engeller. Örneğin, `printf` iç ayırma sağlar. Kanca kodunuzu çağırırsa `printf`, ortaya çıkan ayırma, kanca yeniden çağrılacak olan çağıracak neden olmaz **printf** yeniden vb. kadar yığın taşıyor. Rapora ihtiyacınız varsa `_CRT_BLOCK` ayırma işlemleri, bu kısıtlama aşmak için bir yol olan biçimlendirmek için C çalışma zamanı işlevleri yerine Windows API işlevlerini kullanın ve çıkacağını. Windows API'ları C çalışma zamanı kitaplığı yığın kullanmayın çünkü bunlar, atama kanca sonsuz bir döngüde tuzak değil.  
  
 Çalışma zamanı kitaplığı kaynak dosyaları incelerseniz göreceğiniz işlevi, varsayılan ayırma kanca olduğunu **CrtDefaultAllocHook** (yalnızca döndüren **TRUE**), kendine ait, ayrı bir dosyada bulunan DBGHOOK. C. Bile, uygulamanızın önce yürütülen çalışma zamanı başlatma kodu tarafından yapılan ayırmaları çağrılmasına, atama kanca isteyip istemediğinizi **ana** işlevi, bir kendi yerine bu varsayılan işlev değiştirebilirsiniz kullanarak [_CrtSetAllocHook](http://msdn.microsoft.com/library/405df37b-2fd1-42c8-83bc-90887f17f29d).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama kanca işlevi yazma](../debugger/debug-hook-function-writing.md)   
 [crt_dbg2 örnek](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)



