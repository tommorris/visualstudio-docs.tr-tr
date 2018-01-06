---
title: Idiastackwalkframe::readmemory | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackWalkFrame::readMemory method
ms.assetid: 7ab0b525-a5a7-4692-acad-e8c00fa9ab9a
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: cb4680b84ed3507316d628e8323b71e98cf2ccd3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiastackwalkframereadmemory"></a>IDiaStackWalkFrame::readMemory
Bellek görüntüden okur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT readMemory (   
   MemoryTypeEnum type,  
   ULONGLONG va,  
   DWORD     cbData,  
   DWORD*    pcbData,  
   BYTE      data[]  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `type`  
 [in] Aşağıdakilerden birini [MemoryTypeEnum numaralandırması](../../debugger/debug-interface-access/memorytypeenum.md) erişmek için bellek türünü belirten numaralandırma değerlerinin.  
  
 `va`  
 [in] Okumanın başlatılacağı görüntü konumda sanal adres.  
  
 `cbData`  
 [in] Veri arabelleğinin bayt cinsinden boyutu.  
  
 `pcbData`  
 [out] Döndürülen bayt sayısını döndürür. Varsa `data` olan `NULL`, ardından `pcbData` bayt veri kullanılabilir toplam sayısını içerir.  
  
 `data`  
 [out] Belirtilen konumdan veri ile doldurulacak olan bir arabellek.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)