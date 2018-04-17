---
title: Idiastackwalkhelper::symbolforva | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper::symbolForVA method
ms.assetid: 8dd9455d-d44c-4dd6-a0aa-31131cbea2aa
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a4eca0dd63e70d69c19ec79b5db4bc96d807fb68
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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