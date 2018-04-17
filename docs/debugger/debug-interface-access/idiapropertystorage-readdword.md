---
title: IDiaPropertyStorage::ReadDWORD | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadDWORD
ms.assetid: 5f4c034e-a9d3-4560-94b5-ede524741439
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f456125bffdefe5ebc506774f4ccd3087d571dee
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiapropertystoragereaddword"></a>IDiaPropertyStorage::ReadDWORD
Okur `DWORD` özelliği kümesindeki bir değer.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT ReadDWORD (   
   PROPID id,  
   DWORD* pValue  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Okunacak özellik tanımlayıcısını (`PROPID` WTypes.h tanımlanan bir `ULONG`).  
  
 `pValue`  
 [out] Özellik değeri döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Döndürür `E_INVALIDARG` özellik türü değilse `DWORD`.  
  
## <a name="remarks"></a>Açıklamalar  
 A `DWORD` Windows 32-bit işaretsiz tamsayı olarak tanımlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)