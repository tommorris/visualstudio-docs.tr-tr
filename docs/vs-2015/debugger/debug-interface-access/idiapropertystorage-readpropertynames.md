---
title: IDiaPropertyStorage::ReadPropertyNames | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadPropertyNames
ms.assetid: f8bcab77-afca-4a8f-8710-697842f8a518
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e7f20674da015cb31747afc9cce413d3f2290b5d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628555"
---
# <a name="idiapropertystoragereadpropertynames"></a>IDiaPropertyStorage::ReadPropertyNames
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDiaPropertyStorage::ReadPropertyNames](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiapropertystorage-readpropertynames).  
  
Dize adları için karşılık gelen alır, özellik tanımlayıcıları verilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
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
 [in] Adları alınacağı özellik kimlikleri dizisi (`PROPID` WTypes.h tanımlanan bir `ULONG`).  
  
 `rglpwstrName`  
 [out içinde] Belirtilen özellik kimliklerinin özellik adları dizisi. Dizi istenen sayıda özellik adları tutacak önceden ayrılmış olmalıdır ve en az tutabilecek özellikte `cpropid``BSTR` dizeleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Döndürülen özellik adlarının serbest (çağırarak `SysFreeString` işlevi) artık gerektiğinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)



