---
title: IPerPropertyBrowsing2::GetDisplayString | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IPerPropertyBrowsing2.GetDisplayString
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2::GetDisplayString
ms.assetid: 8f75c6a9-86a9-4e2d-8cb4-74e7b1c0a524
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: be6f665d1f63966b3828868f4fb8fbf1cae002e9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="iperpropertybrowsing2getdisplaystring"></a>IPerPropertyBrowsing2::GetDisplayString
Alır döndürülen metin kendiliğinden görülemeyen türlerini görüntülemek için bir dize özelliği tanımlayan bir ad ve arayanın kullanıcı arabiriminde görüntülenir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetDisplayString(  
   DISPID  dispid,  
   BSTR*  pBstr  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dispid`  
 [in] Görüntü adı istenen özellik tanıtıcısı gönderme.  
  
 `pBstr`  
 [out] İşaretçi `BSTR` tarafından tanımlanan özellik için görünen ad içeren `dispID`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir döndürür `HRESULT`, genellikle `S_OK`.  
  
## <a name="remarks"></a>Açıklamalar  
 Döndürülen dize özelliğinin geçerli bir değer değil. Bu yalnızca bir dize özelliği görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Iperpropertybrowsing2 arabirimi 1](../../winscript/reference/iperpropertybrowsing2-interface-1.md)