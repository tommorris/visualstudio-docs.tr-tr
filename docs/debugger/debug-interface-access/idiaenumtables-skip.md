---
title: Idiaenumtables::Skip | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::Skip method
ms.assetid: 5c9db956-0654-4f1a-8775-530aa980d8ec
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2aadb5570b49c28502f837492657e5301b80616e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiaenumtablesskip"></a>IDiaEnumTables::Skip
Bir numaralandırma sırasını tablolarda belirtilen sayıda atlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT Skip (   
   ULONG celt  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `celt`  
 [in] Atlamak için numaralandırma sırası tablo sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` atlamak için daha fazla tablo varsa.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)