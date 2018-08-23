---
title: IDiaSymbol::get_uavSlot | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: a70648f2-3b25-439f-8099-239ac602515a
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 21e20587e34a518ac4b6e15c55d14f7a477725f1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694400"
---
# <a name="idiasymbolgetuavslot"></a>IDiaSymbol::get_uavSlot
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDiaSymbol::get_uavSlot](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-uavslot).  
  
Uav yuvası alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT get_uavSlot(   
   DWORD* pRetVal);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Bir işaretçi bir `DWORD` uav yuvası tutan.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



