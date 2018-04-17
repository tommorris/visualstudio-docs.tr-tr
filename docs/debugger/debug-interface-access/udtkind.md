---
title: UdtKind | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- UdtKind enumeration
ms.assetid: 400b59b9-373c-42cb-aae1-570494214328
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 29ab87614bad4c73303bb1c7c110d5458598b222
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="udtkind"></a>UdtKind
Kullanıcı tanımlı tür (UDT) çeşitli açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
enum UdtKind {   
   UdtStruct,  
   UdtClass,  
   UdtUnion,  
   UdtInterface  
};  
```  
  
## <a name="elements"></a>Öğeleri  
 UdtStruct  
 UDT bir yapıdır.  
  
 UdtClass  
 UDT bir sınıftır.  
  
 UdtUnion  
 UDT UNION ' dir.  
  
 UdtInterface  
 UDT bir arabirimdir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu numaralandırma değerleri tarafından döndürülen [Idiasymbol::get_udtkind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: cvconst.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar ve yapılar](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_udtKind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)