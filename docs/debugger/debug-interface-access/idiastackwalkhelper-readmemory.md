---
title: IDiaStackWalkHelper::readMemory | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackWalkHelper2::readMemory method
ms.assetid: e1eb90aa-49b7-476c-9e70-7e8f08994cbe
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f528d377dc75f940a10f1a38ae04cc3eb71cdd22
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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