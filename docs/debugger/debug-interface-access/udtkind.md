---
title: UdtKind | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: b95d8bfeda0cd8d5efdaab6d0c2fd13a34c8407c
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31470637"
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