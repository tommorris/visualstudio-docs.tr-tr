---
title: Idiareadexeatrvacallback::readexecutableatrva | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaReadExeAtRVACallback::ReadExecutableAtRVA method
ms.assetid: 3c1e965f-8f05-41a8-86d8-01830b2377c9
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 907b75c6021a739ebbe52cbef1ec3e4714360072
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)