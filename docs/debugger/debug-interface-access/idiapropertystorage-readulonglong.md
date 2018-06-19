---
title: IDiaPropertyStorage::ReadULONGLONG | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadULONGLONG
ms.assetid: f80a2e24-5744-4fec-bab0-3ed51aef6e58
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 35cff5f92f0ceeb15c185316aeb9b9fde155a1ec
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31468862"
---
# <a name="idiapropertystoragereadulonglong"></a>IDiaPropertyStorage::ReadULONGLONG
Okur `ULONGLONG` özelliği kümesindeki bir değer.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT ReadULONGLONG (   
   PROPID     id,  
   ULONGLONG* pValue  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Okunacak özellik tanımlayıcısını (`PROPID` WTypes.h tanımlanan bir `ULONG`).  
  
 `pValue`  
 [out] Özellik değeri döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Döndürür `E_INVALIDARG` özellik türü değilse `ULONGLONG`.  
  
## <a name="remarks"></a>Açıklamalar  
 A `ULONGLONG` Windows 64-bit işaretsiz tamsayı olarak tanımlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)