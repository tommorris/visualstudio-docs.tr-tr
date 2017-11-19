---
title: IDebugProperty::EnumMembers | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugProperty.EnumMembers
apilocation: scrobj.dll
helpviewer_keywords: IDebugProperty::EnumMembers
ms.assetid: 8ce398a5-6452-4804-ae8f-5c54cd11c661
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9cb57f2609fcd9a80e2a9e0dfd63637e6f700047
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugpropertyenummembers"></a>IDebugProperty::EnumMembers
Bir özellik üyeleri numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT EnumMembers (  
   DBGPROP_INFO_FLAGSdwFieldSpec,  
   UINTnRadix,  
   REFIIDrefiid,  
   IEnumDebugPropertyInfo**ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwFieldSpec`  
 [in] Belirtir `DBGPROP_INFO_FLAGS` doldurulacak hangi alanların numaralandırılmış hata ayıklama özelliği yapılarında belirlemek sabitleri.  
  
 `nRadix`  
 [in] Herhangi bir sayısal bilgi yorumlanırken kullanılacak sayı tabanını.  
  
 `refiid`  
 [in] Bu IID Numaralandırıcı filtreleme için geçirilir. IID biri `IDebugPropertyEnumType` devralınmalıdır arabirimleri `IDebugPropertyEnumType_All`.  
  
 `ppEnum`  
 [out] Döndürür `IEnumDebugPropertyInfo` üye özellikleri numaralandırır arabirimi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir döndürür `HRESULT`, genellikle `S_OK`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idebugproperty arabirimi](../../winscript/reference/idebugproperty-interface.md)   
 [DBGPROP_INFO_FLAGS](../../winscript/reference/dbgprop-info-flags.md)   
 [Idebugpropertyenumtype_all arabirimi](../../winscript/reference/idebugpropertyenumtype-all-interface.md)   
 [Ienumdebugpropertyınfo arabirimi](../../winscript/reference/ienumdebugpropertyinfo-interface.md)