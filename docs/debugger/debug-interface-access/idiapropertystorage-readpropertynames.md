---
title: IDiaPropertyStorage::ReadPropertyNames | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadPropertyNames
ms.assetid: f8bcab77-afca-4a8f-8710-697842f8a518
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c1624e3577128556a098f96fd41c9ba1dc1eb84e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiapropertystoragereadpropertynames"></a>IDiaPropertyStorage::ReadPropertyNames
Dize adları için karşılık gelen alır özelliği tanımlayıcıları verilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT ReadPropertyNames (  
   ULONG         cpropid,  
   PROPID const* rgpropid,  
   BSTR*         rglpwstrName  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cpropid`  
 [in] Özellik kimlikleri sayısı `rgpropid`.  
  
 `rgpropid`  
 [in] Özellik kimlikleri adlarını almak istediğiniz için dizisi (`PROPID` WTypes.h tanımlanan bir `ULONG`).  
  
 `rglpwstrName`  
 [içinde out] Belirtilen özellik kimlikleri için özellik adları dizisi. Dizi özellik adları istenen sayıda tutmak için önceden ayrılmış olmalıdır ve en az tutun erişemeyeceksiniz `cpropid``BSTR` dizeleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Döndürülen özellik adları serbest (çağırarak `SysFreeString` işlevi) artık gerek.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)