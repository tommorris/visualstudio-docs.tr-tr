---
title: DiaAddressMapEntry | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: DiaAddressMapEntry enumeration
ms.assetid: 5d0ae226-981d-4541-a801-fc4993fe663b
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f1324ea79ec60a61e315253573b9d4aa3ced2695
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Idiaaddressmap::set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)