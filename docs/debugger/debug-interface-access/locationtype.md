---
title: LocationType | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- LocationType enumeration
ms.assetid: d3e1eedc-bfd3-4c91-881b-d69565138d0f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 82317d6221a8e32bf098e1d8e8a5fdb96d3b1e42
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="locationtype"></a>LocationType
Sembol içerdiği konumu bilgi türünü belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
enum LocationType {   
   LocIsNull,  
   LocIsStatic,  
   LocIsTLS,  
   LocIsRegRel,  
   LocIsThisRel,  
   LocIsEnregistered,  
   LocIsBitField,  
   LocIsSlot,  
   LocIsIlRel,  
   LocInMetaData,  
   LocIsConstant,  
   LocTypeMax  
};  
```  
  
## <a name="elements"></a>Öğeleri  
 `LocIsNull`  
 Konum bilgileri kullanılamıyor.  
  
 `LocIsStatic`  
 Statik konumdur.  
  
 `LocIsTLS`  
 İş parçacığı yerel depolama konumdur.  
  
 `LocIsRegRel`  
 Kayıt göreli konumdur.  
  
 `LocIsThisRel`  
 Konum `this`-göreli.  
  
 `LocIsEnregistered`  
 Bir kayıttaki konumdur.  
  
 `LocIsBitField`  
 Bir bit alanında konumdur.  
  
 `LocIsSlot`  
 Bir Microsoft Ara dili (MSIL) yuva konumdur.  
  
 `LocIsIlRel`  
 MSIL göreli konumdur.  
  
 `LocInMetaData`  
 Meta verilerde konumdur.  
  
 `LocIsConstant`  
 Sabit bir değer konumdur.  
  
 `LocTypeMax`  
 Bu numaralandırma konumu türlerinde sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanılabilir özellikler [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md) simgenin konumu görüntü dosyasının içinde arabirimi bağlıdır. Daha fazla bilgi için bkz: [simge konumları](../../debugger/debug-interface-access/symbol-locations.md).  
  
 Bu numaralandırma değerleri için yapılan bir çağrı tarafından döndürülen [Idiasymbol::get_locationtype](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: cvconst.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar ve yapılar](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [Idiasymbol::get_locationtype](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)   
 [Simge Konumları](../../debugger/debug-interface-access/symbol-locations.md)