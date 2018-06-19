---
title: CV_call_e | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CV_call_e enumeration
ms.assetid: f230560b-4243-432d-8f19-46df112043b9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ccdc9df86180883a5a3891563b22625fab4a2ad2
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31466389"
---
# <a name="cvcalle"></a>CV_call_e
Bir işlev için çağırma kuralı belirtir.  
  
> [!NOTE]
>  Yalnızca en yaygın numaralandırma değerlerinin burada belgelenmiştir. Tam numaralandırma cvconst.h üstbilgi dosyasında kullanılabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
typedef enum CV_call_e {   
   CV_CALL_NEAR_C    = 0x00,  
   CV_CALL_NEAR_FAST = 0x04,  
   CV_CALL_NEAR_STD  = 0x07,  
   CV_CALL_NEAR_SYS  = 0x09,  
   CV_CALL_THISCALL  = 0x0b,  
   CV_CALL_CLRCALL   = 0x16  
} CV_call_e;  
```  
  
## <a name="elements"></a>Öğeleri  
 CV_CALL_NEAR_C  
 Yakın sağdan sola push kullanarak bir işlev çağırma kuralı belirtir. Çağıran işlevi yığını temizler.  
  
 CV_CALL_NEAR_FAST  
 Yazmaçları ile yakın soldan sağa push kullanarak bir işlev çağırma kuralı belirtir. Çağrılan işlev parametre baytları toplamı yığın temizlemek için kullanır.  
  
 CV_CALL_NEAR_STD  
 Yakın standart çağrı (sağdan sola itme) kullanarak bir işlev çağırma kuralı belirtir.  
  
 CV_CALL_NEAR_SYS  
 Yakın bir sistem çağrısı kullanarak bir işlev çağırma kuralı belirtir.  
  
 CV_CALL_THISCALL  
 İşlev çağırma kuralıyla belirtir `this` çağrı (`this` işaretçi geçirilen kaydına).  
  
 CV_CALL_CLRCALL  
 Ortak dil çalışma zamanı (CLR tarafından) (çağırma kuralı olarak da bilinen bir yönetilen kod) kullanılan bir işlev çağırma kuralı belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu numaralandırma değerleri için yapılan bir çağrı tarafından döndürülen [Idiasymbol::get_callingconvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: cvconst.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar ve yapılar](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_callingConvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)