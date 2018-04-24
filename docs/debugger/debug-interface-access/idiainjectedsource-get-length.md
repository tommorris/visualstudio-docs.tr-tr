---
title: Idiaınjectedsource::get_length | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaInjectedSource::get_length method
ms.assetid: 38b88b8b-c2e0-4b2d-8b8b-9ff373733e78
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 09a52457eae3d925b910617cadba12c0bda4c508
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiainjectedsourcegetlength"></a>IDiaInjectedSource::get_length
Kod bayt sayısını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_length (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Kod bayt sayısını döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`. Döndürür `S_FALSE` bu özellik desteklenmiyorsa. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından döndürülen değer kaynak kodu uzunluğu ve tarafından döndürülen değer aynıdır [Idiaınjectedsource::get_source](../../debugger/debug-interface-access/idiainjectedsource-get-source.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaınjectedsource](../../debugger/debug-interface-access/idiainjectedsource.md)   
 [IDiaInjectedSource::get_source](../../debugger/debug-interface-access/idiainjectedsource-get-source.md)