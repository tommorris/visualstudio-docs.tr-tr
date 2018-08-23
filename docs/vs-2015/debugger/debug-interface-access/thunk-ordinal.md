---
title: THUNK_ORDINAL | Microsoft Docs
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
- C++
helpviewer_keywords:
- Thunk_Ordinal enumeration
ms.assetid: 026f98a9-36b8-41ef-8a72-12d7cbc2d362
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cf4a6f96eda9a44e10975ffc1a8262030180b302
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630886"
---
# <a name="thunkordinal"></a>THUNK_ORDINAL
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [thunk_ordınal](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/thunk-ordinal).  
  
Dönüştürücü türlerini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
typedef enum THUNK_ORDINAL {   
   THUNK_ORDINAL_NOTYPE,  
   THUNK_ORDINAL_ADJUSTOR,  
   THUNK_ORDINAL_VCALL,  
   THUNK_ORDINAL_PCODE,  
   THUNK_ORDINAL_LOAD   
  
   // trampoline thunk ordinals - only for use in Trampoline thunk symbols  
   THUNK_ORDINAL_TRAMP_INCREMENTAL,  
   THUNK_ORDINAL_TRAMP_BRANCHISLAND,  
} THUNK_ORDINAL;  
```  
  
## <a name="elements"></a>Öğeleri  
 THUNK_ORDINAL_NOTYPE  
 Standart dönüştürücü.  
  
 THUNK_ORDINAL_ADJUSTOR  
 A `this` adjustor dönüştürücü.  
  
 THUNK_ORDINAL_VCALL  
 Sanal çağrı dönüştürücü.  
  
 THUNK_ORDINAL_PCODE  
 P-code dönüştürücü.  
  
 THUNK_ORDINAL_LOAD  
 Gecikme yükü dönüştürücü.  
  
 THUNK_ORDINAL_TRAMP_INCREMENTAL  
 Artımlı trampoline dönüştürücü (trampoline dönüştürücü çağrıları bir bellek alanından Sıçrama için kullanılır).  
  
 THUNK_ORDINAL_TRAMP_BRANCHISLAND  
 Dal noktası trampoline dönüştürücü.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sabit listesi değerleri çağrısından döndürülen [Idiasymbol::get_thunkordinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: cvconst.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri ve yapıları](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_thunkOrdinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)



