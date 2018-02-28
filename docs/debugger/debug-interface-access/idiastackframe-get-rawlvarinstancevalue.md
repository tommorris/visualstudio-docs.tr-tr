---
title: "Idiastackframe::get_rawlvarınstancevalue | Microsoft Docs"
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
- IDiaStackFrame::get_rawLVarInstanceValue method
ms.assetid: ce526259-85a6-475b-9274-0b3a21d95db2
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5872c77a9154c72f6c3bcd76452792cff34452cb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiastackframegetrawlvarinstancevalue"></a>IDiaStackFrame::get_rawLVarInstanceValue
Bu yöntem, ham bayt olarak belirtilen yerel değişkenin değerini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_rawLVarInstanceValue(  
   IDiaLVarInstance* pInstance,  
   DWORD             cbDataMax,  
   DWORD*            pcbData,  
   BYTE*             pbData  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pInstance`  
 [in] Bir `IDiaLVarInstance` değerini almak için yerel değişken örneğini temsil eden nesne.  
  
 `cbDataMax`  
 [in] Tarafından arabellekteki bayt sayısını işaret için `pbData`. Bu en fazla 8 bayt olabilir (`sizeof(ULONGLONG)`).  
  
 `pcbData`  
 [out] Arabellekte depolanan bayt sayısını döndürür.  
  
 `pbData`  
 [out] Veri ile doldurulacak arabellek. Bu olamaz `NULL`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)