---
title: Idiastackframe::get_rawlvarınstancevalue | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_rawLVarInstanceValue method
ms.assetid: ce526259-85a6-475b-9274-0b3a21d95db2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2c50b1db74674158d4c7304bbacb4105f387cd56
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31466857"
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