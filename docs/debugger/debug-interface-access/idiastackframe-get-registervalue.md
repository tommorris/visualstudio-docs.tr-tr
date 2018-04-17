---
title: Idiastackframe::get_registervalue | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_registerValue method
ms.assetid: cbe3d8ac-319a-40ac-bc3e-4eb81b2d7807
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e38d94d5c79438b103b4db9a16164ffe482c356b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiastackframegetregistervalue"></a>IDiaStackFrame::get_registerValue
Belirtilen bir kayıt değeri yığın çerçevesinde depolanmış olarak alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_registerValue(  
   ULONG      registerIndex,  
   ULONGLONG *pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `registerIndex`  
 [in] Aşağıdakilerden birini [CV_HREG_e numaralandırması](../../debugger/debug-interface-access/cv-hreg-e.md) numaralandırma değerleri.  
  
 `pRetVal`  
 [out] Kayıt defterinde depolanan değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde, hata kodunu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiastackframe](../../debugger/debug-interface-access/idiastackframe.md)   
 [CV_HREG_e numaralandırması](../../debugger/debug-interface-access/cv-hreg-e.md)