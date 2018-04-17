---
title: IDiaStackWalkHelper::readMemory | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::readMemory method
ms.assetid: e1eb90aa-49b7-476c-9e70-7e8f08994cbe
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: af93d4d49167a6167d971140c3b668c95a34f799
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiastackwalkhelperreadmemory"></a>IDiaStackWalkHelper::readMemory
Bir veri bloğunun bellekte çalıştırılabilir programın görüntüden okur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT readMemory(   
   enum MemoryTypeEnum type,  
   ULONGLONG           va,  
   DWORD               cbData,  
   DWORD*              pcbData,  
   BYTE*               pbData  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `type`  
 [in] Arasında bir değer [MemoryTypeEnum numaralandırması](../../debugger/debug-interface-access/memorytypeenum.md) okumak için bellek türünü belirleyen numaralandırması.  
  
 Va  
 [in] Sanal adres okuma başlayacağı görüntüsündeki.  
  
 `cbData`  
 [in] Veri arabelleğinin bayt cinsinden boyutu.  
  
 `pcbData`  
 [out] Gerçekte okunan bayt sayısını döndürür. Varsa `pbData` olan `NULL`, sonra bu verilerin kullanılabilir bayt sayısı.  
  
 `pbData`  
 [içinde out] Okuma bellek bilgileriyle doldurulan bir arabellek.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [MemoryTypeEnum numaralandırması](../../debugger/debug-interface-access/memorytypeenum.md)