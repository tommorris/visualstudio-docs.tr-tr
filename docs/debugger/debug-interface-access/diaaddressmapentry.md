---
title: DiaAddressMapEntry | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: 0a29de8f18a9d3123d73210d0e362c2ae2d32641
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31459811"
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