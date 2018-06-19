---
title: IDebugProperty::GetExtendedInfo | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugProperty.GetExtendedInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugProperty::GetExtendedInfo
ms.assetid: a989ade5-16d5-4ee6-8d8a-8dcbfad24034
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cc549ecc4cfa3b3cbbb754585c751b16df2fd8a6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24794321"
---
# <a name="idebugpropertygetextendedinfo"></a>IDebugProperty::GetExtendedInfo
Genişletilmiş özellik bilgilerini.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetExtendedInfo (  
   ULONG  cInfos,  
   GUID*  rgguidExtendedInfo,  
   VARIANT* pExtendedInfo  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cInfos`  
 [in] Genişletilmiş bilgi nesnelerinin sayısı.  
  
 `rgguidExtendedInfo`  
 [in] Bir dizi `GUID`s, böylece aynı anda birden çok öğe genişletilmiş bilgisi alınabilir geçirilir.  
  
 `pExtendedInfo`  
 [out] Bir dizi döndürür `VARIANT`genişletilmiş özellik bilgilerini almak için kullanılan s.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir döndürür `HRESULT`, genellikle `S_OK`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim, bu nesne için bilgi genişletilmiş. API var. yalnızca kendisi tarafından kullanımını alınan için ödünç değil bilgi almak amacıyla `IDebugProperty::GetPropertyInfo`).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idebugproperty arabirimi](../../winscript/reference/idebugproperty-interface.md)