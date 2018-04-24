---
title: IDiaPropertyStorage::ReadBSTR | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadBSTR
ms.assetid: 7214643b-3286-48ed-90aa-0fe95b4cae5b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7711042d3e3c6ef6d5b785bb6f9c1bf3f29a3399
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiapropertystoragereadbstr"></a>IDiaPropertyStorage::ReadBSTR
Okur `BSTR` özelliği kümesindeki bir değer.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT ReadBSTR (   
   PROPID id,  
   BSTR*  pValue  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Okunacak özellik tanımlayıcısını (`PROPID` WTypes.h tanımlanan bir `ULONG`).  
  
 `pValue`  
 [out] Özellik değeri döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Döndürür `E_INVALIDARG` özellik türü değilse `BSTR`.  
  
## <a name="remarks"></a>Açıklamalar  
 A `BSTR` sıfır sonlandırılan geniş karakter dizesi şeklinde Windows tarafından tanımlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)