---
title: Idiastackwalkhelper::symbolforva | Microsoft Docs
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
- IDiaStackWalkHelper::symbolForVA method
ms.assetid: 8dd9455d-d44c-4dd6-a0aa-31131cbea2aa
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 43361f7fb002a753d7fc4fb59f8d3cd9839ceb49
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiastackwalkhelpersymbolforva"></a>IDiaStackWalkHelper::symbolForVA
Belirtilen sanal adres içeren simge alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT symbolForVA(   
   ULONGLONG     va,  
   IDiaSymbol**  ppSymbol  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `va`  
 [in] İstenen sembolü bulunan sanal adres. Simgenin olmalıdır bir `SymTagFunctionType` (arasında bir değer [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) numaralandırması).  
  
 `ppSymbol`  
 [out] Bir [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md) belirtilen adresteki simgenin temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)