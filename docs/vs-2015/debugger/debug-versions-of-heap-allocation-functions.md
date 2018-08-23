---
title: Hata ayıklama yığın ayırma işlevleri sürümleri | Microsoft Docs
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
- vs.debug.crt
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- _CRTDBG_MAP_ALLOC macro
- debugging [CRT], heap allocation functions
- debugging memory leaks, CRT debug library functions
- malloc function
- memory leaks, CRT debug library functions
- heap allocation, debug
- _malloc_dbg function
ms.assetid: 91748bdc-f4cd-4d8b-ab98-0493dab7ed0d
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c16bc2b1c887b8a33f907dd574ac647c5e0ffbc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693027"
---
# <a name="debug-versions-of-heap-allocation-functions"></a>Öbek Atama İşlevleri Hata Ayıklama Sürümleri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata ayıklama sürümleri, yığın ayırma işlevleri](https://docs.microsoft.com/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
C çalışma zamanı kitaplığı, özel öbek atama işlevleri hata ayıklama sürümlerini içerir. Bu işlevler sürümle aynı ada sahip sürümleri _dbg eklenir. Bu konuda bir CRT işlevini sürümü _dbg sürümü arasındaki farkları açıklar kullanarak `malloc` ve `_malloc_dbg` örnekler.  
  
 Zaman [_DEBUG](http://msdn.microsoft.com/library/a9901568-4846-4731-a404-399d947e2e7a) olan tanımlanan, CRT tüm eşler [malloc](http://msdn.microsoft.com/library/144fcee2-be34-4a03-bb7e-ed6d4b99eea0) çağrılar [_malloc_dbg](http://msdn.microsoft.com/library/c97eca51-140b-4461-8bd2-28965b49ecdb). Bu nedenle, kodu kullanarak yeniden gerekmez `_malloc_dbg` yerine `malloc` hata ayıklama sırasında avantajlardan yararlanabilir.  
  
 Çağırmak isteyebilirsiniz `_malloc_dbg` açıkça ancak. Çağırma `_malloc_dbg` açıkça bazı avantajları eklemiştir:  
  
-   İzleme `_CLIENT_BLOCK` ayırmaları yazın.  
  
-   Ayırma isteği gerçekleştiği kaynak dosya ve satır numarası depolama.  
  
 Dönüştürmek istemiyorsanız, `malloc` çağrılar `_malloc_dbg`, tanımlayarak, kaynak dosya bilgileri edinebilirsiniz [_CRTDBG_MAP_ALLOC](http://msdn.microsoft.com/library/435242b8-caea-4063-b765-4a608200312b), tüm çağrıları doğrudan önişlemci harita neden `malloc` için`_malloc_dbg` çevresinde bir sarmalayıcı güvenmek yerine `malloc`.  
  
 İstemci bloklarında ayırmaları ayrı türlerini izlemek için çağırmalıdır `_malloc_dbg` doğrudan ve `blockType` parametresi `_CLIENT_BLOCK`.  
  
 _DEBUG tanımlı değil, çağrılar `malloc` değil etkilenir, çağrılar `_malloc_dbg` için çözümlendiği `malloc`, tanımını [_CRTDBG_MAP_ALLOC](http://msdn.microsoft.com/library/435242b8-caea-4063-b765-4a608200312b) göz ardı edilir ve kaynak dosya bilgileri saklamanıza ayırma isteği belirtilmedi. Çünkü `malloc` blok türü parametresi yok, için istekleri `_CLIENT_BLOCK` türler standart ayırmaları kabul edilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRT hata ayıklama teknikleri](../debugger/crt-debugging-techniques.md)



