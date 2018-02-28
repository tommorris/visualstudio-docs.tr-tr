---
title: IDiaPropertyStorage::ReadPropertyNames | Microsoft Docs
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
- IDiaPropertyStorage::ReadPropertyNames
ms.assetid: f8bcab77-afca-4a8f-8710-697842f8a518
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 95f535bd314ec998c83ec9c02aab2190646f3c53
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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