---
title: MemoryTypeEnum | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MemoryTypeEnum enumeration
ms.assetid: 8778c047-edeb-4495-8f9f-3f8bbb297099
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 92eaaa63f276d9107dfa3155eb85d52884d3157c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="memorytypeenum"></a>MemoryTypeEnum
Erişim için bellek türünü belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
enum MemoryTypeEnum {  
   MemTypeCode,  
   MemTypeData,  
   MemTypeStack,  
   MemTypeAny = -1  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 `MemTypeCode`  
 Erişimi yalnızca bellek kodu.  
  
 `MemTypeData`  
 Veri ya da yığın bellek erişir.  
  
 `MemTypeStack`  
 Erişimi yalnızca bellek yığın.  
  
 `MemTypeAny`  
 Bellek her türlü erişir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu numaralandırma değerleri geçirilecek [IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md) bellek farklı türlerde erişimi sınırlamak için yöntem.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: cvconst.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar ve yapılar](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md)