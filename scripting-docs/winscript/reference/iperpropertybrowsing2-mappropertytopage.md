---
title: IPerPropertyBrowsing2::MapPropertyToPage | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IPerPropertyBrowsing2.MapPropertyToPage
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2::MapPropertyToPage
ms.assetid: e6418a8e-500b-42e1-9b5a-52e6f7567f99
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 79b8d7cb9e1c8a9f79cdddc4f8d3404ff7a2036c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="iperpropertybrowsing2mappropertytopage"></a>IPerPropertyBrowsing2::MapPropertyToPage
Bu özellik düzenlemek için kullanılan özellik sayfası CLSID döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT MapPropertyToPage(  
   DISPID  dispid,  
   CLSID*  pClsidPropPage  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dispid`  
 [in] Özellik ilgi tanıtıcısı gönderme.  
  
 `pClsidPropPage`  
 [out] Özellik ile ilişkilendirilmiş özellik sayfası tanımlayan CLSID işaretçi. Bu yöntem başarısız olursa, *`pClsidPropPage` CLSID_NULL için ayarlanır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir döndürür `HRESULT`, genellikle `S_OK`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Iperpropertybrowsing2 arabirimi 1](../../winscript/reference/iperpropertybrowsing2-interface-1.md)