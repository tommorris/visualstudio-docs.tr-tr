---
title: IPerPropertyBrowsing2::SetPredefinedValue | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IPerPropertyBrowsing2.SetPredefinedValue
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2::SetPredefinedValue
ms.assetid: 3aff5300-c5a4-4d9b-9d47-a75b64014ac4
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aed28237fe8e2be5789e062aed01e428ce805790
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24794612"
---
# <a name="iperpropertybrowsing2setpredefinedvalue"></a>IPerPropertyBrowsing2::SetPredefinedValue
Tarafından belirtilen özellik değerini ayarlar `dispID`. Önceden tanımlanmış değer belirtecin tarafından tanımlanır`dwCookie.`  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT SetPredefinedValue(  
   DISPID  dispid,  
   DWORD  dwCookie  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dispid`  
 [in] Önceden tanımlanmış bir değer ayarlanmış özellik tanımlayıcısı gönderme.  
  
 `dwCookie`  
 [in] Ayarlanacak değer tanımlama belirteci.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir döndürür `HRESULT`, genellikle `S_OK`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Iperpropertybrowsing2 arabirimi 1](../../winscript/reference/iperpropertybrowsing2-interface-1.md)