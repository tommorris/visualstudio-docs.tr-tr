---
title: DiaAddressMapEntry | Microsoft Docs
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
- DiaAddressMapEntry enumeration
ms.assetid: 5d0ae226-981d-4541-a801-fc4993fe663b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 2d6886ed55fbe8c48beabf81144a9551efa1a562
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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