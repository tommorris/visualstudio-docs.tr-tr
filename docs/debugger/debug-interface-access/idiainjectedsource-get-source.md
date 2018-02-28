---
title: "Idiaınjectedsource::get_source | Microsoft Docs"
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
- IDiaInjectedSource::get_source method
ms.assetid: 3c0b5386-321f-4f8f-85cc-e2ee7b4cc3d2
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c58989c6958aa8a604f5e7c7a9ef5c4d3eb84f1f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiainjectedsourcegetsource"></a>IDiaInjectedSource::get_source
Kaynak kodu bayt alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_source (   
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cbData`  
 [in] Veri arabellek boyutu temsil eden bayt sayısı.  
  
 `pcbData`  
 [out] Döndürülen bayt sayısını temsil eder bayt sayısı döndürür. Varsa `data` olan `NULL`, ardından `pcbData` veri baytı sayısı toplam kullanılabilir.  
  
 `data[]`  
 [out] Oturum kaynak bayt doldurulması için arabellek.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`. Döndürür `S_FALSE` bu özellik desteklenmiyorsa. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)