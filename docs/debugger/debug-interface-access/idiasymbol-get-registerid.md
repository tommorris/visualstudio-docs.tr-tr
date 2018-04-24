---
title: Idiasymbol::get_registerıd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_registerId method
ms.assetid: f881e793-eb9e-48dc-a847-dd61d77174fc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8f6a4583206666f90adb90cbebebf9417e66fc78
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasymbolgetregisterid"></a>IDiaSymbol::get_registerId
Konumun kayıt Belirleyicisi alır, [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md) ayarlanır `LocIsEnregistered`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_registerId (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Konumun kayıt Belirleyicisi döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
> [!NOTE]
>  Dönüş değeri `S_FALSE` özelliği simgesi kullanılabilir olmadığı anlamına gelir.  
  
## <a name="remarks"></a>Açıklamalar  
 Simge bir kayıt göre diğer bir deyişle, ise, simgenin [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md) ayarlanır `LocIsRegRel`, kullanın `get_registerId` yöntemi için bir çağrı tarafından izlenen [Idiasymbol::get_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md) simgenin bulunduğu kasadan uzaklık almak için yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md)