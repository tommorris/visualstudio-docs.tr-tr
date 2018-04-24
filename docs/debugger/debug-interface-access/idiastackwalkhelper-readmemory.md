---
title: IDiaStackWalkHelper::readMemory | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: 14a8e435dddaf0d6fb3908a1ccb6233f08ccd28b
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
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