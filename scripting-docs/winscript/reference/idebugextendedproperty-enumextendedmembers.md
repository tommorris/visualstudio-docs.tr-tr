---
title: IDebugExtendedProperty::EnumExtendedMembers | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugExtendedProperty.EnumExtendedMembers
apilocation: scrobj.dll
helpviewer_keywords: IDebugExtendedProperty::EnumExtendedMembers
ms.assetid: 27cdb091-da4e-44d2-a631-31ae00468b98
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 81b1cbb9b36d7ae237551aad2677f9480c615b88
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugextendedpropertyenumextendedmembers"></a>IDebugExtendedProperty::EnumExtendedMembers
Genişletilmiş özellik üyeleri numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT EnumExtendedMembers(  
   EX_DBGPROP_INFO_FLAGS  dwFieldSpec,  
   UINT  nRadix,  
   IEnumDebugExtendedPropertyInfo**  ppeepi  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwFieldSpec`  
 [in] Hata ayıklama özelliği yapıları numaralandırılmış alanları genişletilmiş belirlemek EX_DBGPROP_INFO_FLAGS sabitleri doldurulacak belirtir.  
  
 `nRadix`  
 [in] Herhangi bir sayısal bilgi yorumlanırken kullanılacak sayı tabanını.  
  
 `ppeepi`  
 [out] Döndürür `IEnumDebugExtendedPropertyInfo` üye özellikleri numaralandırır arabirimi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir döndürür `HRESULT`, genellikle `S_OK`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idebugextendedproperty arabirimi](../../winscript/reference/idebugextendedproperty-interface.md)   
 [EX_DBGPROP_INFO_FLAGS](../../winscript/reference/ex-dbgprop-info-flags.md)   
 [Extendeddebugpropertyınfo yapısı](../../winscript/reference/extendeddebugpropertyinfo-structure.md)