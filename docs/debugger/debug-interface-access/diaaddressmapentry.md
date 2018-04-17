---
title: DiaAddressMapEntry | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DiaAddressMapEntry enumeration
ms.assetid: 5d0ae226-981d-4541-a801-fc4993fe663b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bc13e8813c0e1bddd1f6cb9abd3d70b26eb5a8e1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="diaaddressmapentry"></a>DiaAddressMapEntry
Bir adres eşlemesi bir girişe açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
struct DiaAddressMapEntry {   
   DWORD rva,  
   DWORD rvaTo  
};  
```  
  
## <a name="elements"></a>Öğeleri  
 `rva`  
 A. görüntüsündeki göreli sanal adres (RAV)  
  
 `rvaTo`  
 Göreli sanal adres `rva` görüntü B. eşlendi  
  
## <a name="remarks"></a>Açıklamalar  
 Bir adres eşlemesi tek bir görüntü düzeninden çeviri (A) için başka bir (B) sağlar. Bir dizi `DiaAddressMapEntry` göre sıralanmış yapıları `rva` bir adres eşlemesi tanımlar.  
  
 Bir adresi çevirmek için `addrA`, bir adresi için bir görüntüde `addrB`, görüntü B, aşağıdaki adımları gerçekleştirin:  
  
1.  Eşleme girişi için arama `e`, en büyük ile `rva` küçük veya eşit `addrA`.  
  
2.  Ayarlama `delta = addrA - e.rva`.  
  
3.  Ayarlama `addrB = e.rvaTo + delta`.  
  
 Bir dizi `DiaAddressMapEntry` yapıları iletilir [Idiaaddressmap::set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: dia2.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar ve yapılar](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)