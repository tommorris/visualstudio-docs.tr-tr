---
title: DataKind | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DataKind enumeration
ms.assetid: b64be708-22d6-4360-99e7-8f4e6b196de7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 508058a85d60645fca5e50bc1e6c456da7df7b26
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="datakind"></a>DataKind
Belirli bir veri değeri kapsamını gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
enum DataKind {   
   DataIsUnknown,  
   DataIsLocal,  
   DataIsStaticLocal,  
   DataIsParam,  
   DataIsObjectPtr,  
   DataIsFileStatic,  
   DataIsGlobal,  
   DataIsMember,  
   DataIsStaticMember,  
   DataIsConstant  
};  
```  
  
## <a name="elements"></a>Öğeleri  
 DataIsUnknown  
 Veri simgesi belirlenemiyor.  
  
 DataIsLocal  
 Veri öğesi yerel bir değişkendir.  
  
 DataIsStaticLocal  
 Veri öğesi bir statik yerel değişkendir.  
  
 DataIsParam  
 Veri öğesi bir resmi bir parametredir.  
  
 DataIsObjectPtr  
 Veri öğesi olan bir nesne işaretçisi (`this`).  
  
 DataIsFileStatic  
 Veri öğesi dosya kapsamlı bir değişkendir.  
  
 DataIsGlobal  
 Veri öğesi genel bir değişkendir.  
  
 DataIsMember  
 Veri, bir nesne üye değişkeni öğesidir.  
  
 DataIsStaticMember  
 Veri öğesi bir sınıf statik değişkendir.  
  
 DataIsConstant  
 Veri öğesi sabit bir değerdir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu numaralandırma değerleri tarafından döndürülen [Idiasymbol::get_datakind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: cvconst.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar ve yapılar](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)