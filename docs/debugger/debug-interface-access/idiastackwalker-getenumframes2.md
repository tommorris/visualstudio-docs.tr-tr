---
title: IDiaStackWalker::getEnumFrames2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalker2::getEnumFrames2 method
ms.assetid: 73196d3f-112c-4b3a-997b-7c6b815d4afc
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 85e003259f5a9f04a83f5a46433001fad12b6711
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiastackwalkergetenumframes2"></a>IDiaStackWalker::getEnumFrames2
Belirli platform türü için bir yığın çerçeve Numaralayıcı alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
  
      HRESULT getEnumFrames2(   
   enum  CV_CPU_TYPE_e    cpuid,  
   IDiaStackWalkHelper*   pHelper,  
   IDiaEnumStackFrames**  ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cpuid`  
 [in] Arasında bir değer [CV_CPU_TYPE_e numaralandırması](../../debugger/debug-interface-access/cv-cpu-type-e.md) platform türünü belirten numaralandırma.  
  
 `pHelper`  
 [in] Yardımcı [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md) nesnesi.  
  
 `ppEnum`  
 [out] Döndürür bir [Idiaenumstackframes](../../debugger/debug-interface-access/idiaenumstackframes.md) listesini içeren bir nesne [Idiastackframe](../../debugger/debug-interface-access/idiastackframe.md) nesneleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Yalnızca x86 için yığın çerçeve listesini almak için platform, çağrı [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiastackwalker](../../debugger/debug-interface-access/idiastackwalker.md)   
 [CV_CPU_TYPE_e numaralandırması](../../debugger/debug-interface-access/cv-cpu-type-e.md)   
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [Idiastackframe](../../debugger/debug-interface-access/idiastackframe.md)   
 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)