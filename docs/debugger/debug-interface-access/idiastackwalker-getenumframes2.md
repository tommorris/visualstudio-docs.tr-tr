---
title: IDiaStackWalker::getEnumFrames2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalker2::getEnumFrames2 method
ms.assetid: 73196d3f-112c-4b3a-997b-7c6b815d4afc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 834b202d406ce7ae2e2a5b2ec80b8f7c46f0f576
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
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