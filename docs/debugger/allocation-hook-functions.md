---
title: "Atama kanca işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- memory allocation, logging allocation information
- insufficient memory
- debugging [C++], hook functions
- _CrtSetAllocHook function
- allocation hooks
- hooks, allocation
ms.assetid: 6bfbdb65-8cb1-4c21-8c45-7194a2b77c1e
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9147439d6aab7a6393f37f0cf8b14b0b0401ed1e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="allocation-hook-functions"></a>Atama Kanca İşlevleri
Kullanılarak yüklenen bir ayırma kanca işlevini [_CrtSetAllocHook](/cpp/c-runtime-library/reference/crtsetallochook), bellek tahsis, yeniden tahsis veya serbest her zaman çağrılır. Kanca bu tür birçok farklı amaçlar için kullanılabilir. Uygulama yetersiz bellek durumlarda, örneğin, işleme biçimini test etmek veya ayırma desenleri incelemek için ya da daha sonraki analizler için ayırma bilgileri günlüğe kaydetmek için kullanın.  
  
> [!NOTE]
>  C çalışma zamanı kitaplığı işlevleri açıklandığı bir ayırma kanca işlevini kullanarak hakkında kısıtlama haberdar [ayırma kanca oluşturur ve C çalışma zamanı bellek ayırmaları](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md).  
  
 Bir ayırma kanca işlevini prototip aşağıdaki gibi olmalıdır:  
  
```  
int YourAllocHook(int nAllocType, void *pvData,  
        size_t nSize, int nBlockUse, long lRequest,  
        const unsigned char * szFileName, int nLine )  
```  
  
 Geçirdiğiniz işaretçiyi [_CrtSetAllocHook](/cpp/c-runtime-library/reference/crtsetallochook) türü **_CRT_ALLOC_HOOK**, CRTDBG içinde tanımlanan. Y:  
  
```  
typedef int (__cdecl * _CRT_ALLOC_HOOK)  
    (int, void *, size_t, int, long, const unsigned char *, int);  
```  
  
 Çalışma zamanı kitaplığı, kanca çağırdığında *nAllocType* bağımsız değişkeni gösterir hangi ayırma işlemidir hakkında gerçekleştirilecek (**_HOOK_ALLOC**, **_HOOK_REALLOC**, veya **_HOOK_FREE**). Ücretsiz bir ya da yeniden ayırma, söz konusu olduğunda `pvData` hakkında boşaltılacak blok kullanıcı konu bir işaretçi içeriyor. Ancak, bir ayırma söz konusu olduğunda, ayırma değil henüz oluştuğu için this işaretçisi null olur. Kalan bağımsız değişkenleri ayırma boyutu söz konusu kendi blok türü varsa ve bir işaretçi ayırma yapıldığı, dosya adı ve satır numarası ile ilişkili sıralı istek numarasını içerir. Kanca işlevini ne olursa olsun çözümleme yapar ve diğer kendi Yazar istediği görevleri sonra ya da döndürmelidir **TRUE**, ayırma işlemi devam edebilir, gösteren veya **yanlış**, belirten, işlem başarısız olmalıdır. Bu tür bir basit kancası kadarki ayrılan bellek miktarını denetle ve geri dönüp **FALSE** bu tutar küçük bir sınır aşılırsa. Uygulama sonra yalnızca kullanılabilir bellek yetersiz olduğu zaman, normal olarak ortaya çıkabilecek ayırma hataları tür deneyimi. Daha karmaşık kancaları ayırma desenleri izlemek, bellek kullanımını çözümleme veya özel durumlar ortaya çıktığında rapor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ayırma kancaları ve C çalışma zamanı bellek ayırmaları](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)   
 [Hata ayıklama kanca işlevi yazma](../debugger/debug-hook-function-writing.md)   
 [crt_dbg2 örnek](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)