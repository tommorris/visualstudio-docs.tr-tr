---
title: "Idiasymbol::get_registerıd | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_registerId method
ms.assetid: f881e793-eb9e-48dc-a847-dd61d77174fc
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5fe8b131e715f5fa55d2d2f99cb8c4714996290
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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