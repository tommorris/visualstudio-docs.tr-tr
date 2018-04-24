---
title: Ayırma kancaları ve C çalışma zamanı bellek ayırmaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], hook functions
- memory allocation, troubleshooting allocation hooks
- allocation hooks
- hooks, allocation
ms.assetid: cc34ee96-3d91-41bd-a019-aa3759139e7e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2b0d4a14ff8df32ea783f74bd911ba97fa179563
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="allocation-hooks-and-c-run-time-memory-allocations"></a>Atama Kancaları ve C Çalışma Zamanı Bellek Ayırmaları
Bunlar açıkça yoksay gerekir, atama kanca işlevleri üzerinde çok önemli bir kısıtlamadır ise `_CRT_BLOCK` bloklar (C çalışma zamanı kitaplığı işlevleri tarafından dahili olarak yapılan bellek ayırmaları) tahsis C çalışma zamanı kitaplığı işlevleri yapılan her çağrı yaparsanız iç bellek. `_CRT_BLOCK` Blokları gibi işlevi aşağıdaki değerlerin başındaki kanca kod dahil göz ardı:  
  
```  
if ( nBlockUse == _CRT_BLOCK )  
    return( TRUE );  
```  
  
 Atama kanca değil yoksayarsanız `_CRT_BLOCK` , kanca adlı herhangi bir C çalışma zamanı kitaplığı işlev sonsuz bir döngüde programa yakalayabilir sonra engeller. Örneğin, `printf` bir iç ayırma yapar. Kanca kodunuzu çağırırsa `printf`, sonuçta elde edilen ayırma, kanca yeniden çağrılacak olan çağıracak neden olmaz **printf** yeniden vb. yığın taşar kadar. Rapor için gerekiyorsa `_CRT_BLOCK` ayırma işlemleri, bu kısıtlamayı aşmak için bir yoldur biçimlendirmek için C çalışma zamanı işlevleri yerine Windows API işlevleri kullanın ve çıkış. Windows API'ları C çalışma zamanı kitaplığı yığın kullanmadığından, bunlar, atama kanca sonsuz bir döngüde içinde yakalamasını değil.  
  
 Çalışma zamanı kitaplığı kaynak dosyaları incelerseniz göreceğiniz varsayılan ayırma kanca olduğunu işlevi, **CrtDefaultAllocHook** (yalnızca döndüren **TRUE**), kendi, ayrı bir dosyada bulunan DBGHOOK. C Bile, uygulamanızın önce yürütülür çalıştırma başlangıç kodu tarafından yapılan ayırmaları için çağrılacak, atama kanca isteyip istemediğinizi **ana** işlevi, biri ile kendi yerine bu varsayılan işlevini değiştirebilirsiniz kullanarak [_CrtSetAllocHook](/cpp/c-runtime-library/reference/crtsetallochook).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama kanca işlevi yazma](../debugger/debug-hook-function-writing.md)   
