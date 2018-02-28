---
title: IDiaPropertyStorage::ReadLONG | Microsoft Docs
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
- IDiaPropertyStorage::ReadLONG
ms.assetid: 32054cbc-db55-4513-a1b4-de80e77aac8a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: fca0d07dab3559bbd806a6eb5a34b2a9dbe466eb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiapropertystoragereadlong"></a>IDiaPropertyStorage::ReadLONG
Okur `LONG` özelliği kümesindeki bir değer.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT ReadDLONG (   
   PROPID id,  
   LONG*  pValue  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Okunacak özellik tanımlayıcısını (`PROPID` WTypes.h tanımlanan bir `ULONG`).  
  
 `pValue`  
 [out] Özellik değeri döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Döndürür `E_INVALIDARG` özellik türü değilse `LONG`.  
  
## <a name="remarks"></a>Açıklamalar  
 A `LONG` Windows 32-bit işaretli tamsayıyı olarak tanımlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)