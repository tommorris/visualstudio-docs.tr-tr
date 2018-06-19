---
title: Atama kanca işlevleri | Microsoft Docs
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
- memory allocation, logging allocation information
- insufficient memory
- debugging [C++], hook functions
- _CrtSetAllocHook function
- allocation hooks
- hooks, allocation
ms.assetid: 6bfbdb65-8cb1-4c21-8c45-7194a2b77c1e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6c46b498ea36459dff0eb538ac3e0371fd9c5707
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31460114"
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
