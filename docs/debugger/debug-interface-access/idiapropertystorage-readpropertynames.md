---
title: IDiaPropertyStorage::ReadPropertyNames | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: a13ac0e3a1af8dc20fe63f832e7a19d7bf40c271
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31465583"
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