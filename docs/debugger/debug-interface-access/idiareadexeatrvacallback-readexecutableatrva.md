---
title: Idiareadexeatrvacallback::readexecutableatrva | Microsoft Docs
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
- IDiaReadExeAtRVACallback::ReadExecutableAtRVA method
ms.assetid: 3c1e965f-8f05-41a8-86d8-01830b2377c9
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 71dd19f15d631c58e99a826ab1ff274b993afd5e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiareadexeatrvacallbackreadexecutableatrva"></a>IDiaReadExeAtRVACallback::ReadExecutableAtRVA
Belirtilen sayıda baytı belirtilen göreli sanal adresinden (RAV) yürütülebilir dosyası başlayarak okur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT ReadExecutableAtRVA (   
   DWORD  relativeVirtualAddress,  
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `relativeVirtualAddress`  
 [in] Okumanın başlatılacağı RVA yürütülebilir dosya.  
  
 `cbData`  
 [in] Okunacak bayt sayısı.  
  
 `pcbData`  
 [out] Okunan bayt sayısını döndürür.  
  
 `data[]`  
 [içinde out] Dosyadan okunan bayt bilgileriyle doldurulan bir dizi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, göreli bir sanal adresini kullanarak bir yürütülebilir dosyadan veri baytı yüklemek için DIA destek kodu tarafından çağrılır. Support, bu yöntem çağrılır [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiareadexeatrvacallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)