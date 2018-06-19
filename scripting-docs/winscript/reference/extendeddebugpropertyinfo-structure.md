---
title: Extendeddebugpropertyınfo yapısı | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ExtendedDebugPropertyInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- ExtendedDebugPropertyInfo structure
ms.assetid: f2cf6477-454b-4d13-95da-ae4c90daa175
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ee06b0ace93f068e0530a3aa62b8c28d11069f44
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791918"
---
# <a name="extendeddebugpropertyinfo-structure"></a>ExtendedDebugPropertyInfo Yapısı
Genişletir `DebugPropertyInfo` genişletilmiş özellik ayırdetmek için ek üyeleriyle yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct ExtendedDebugPropertyInfo{  
   DBGPROP_INFO_FLAGS  dwValidFields;  
   LPOLESTR  bstrName;  
   LPOLESTR  bstrType;  
   LPOLESTR  bstrValue;  
   LPOLESTR  bstrFullName;  
   DBGPROP_ATTRIB_FLAGS  dwAttrib;  
   IDebugProperty*  pDebugProp;  
   DWORD  nDISPID;  
   DWORD  nType;  
   VARIANT  varValue;  
   ILockBytes*  plbValue;  
   IDebugExtendedProperty*  pDebugExtProp;  
};  
```  
  
## <a name="members"></a>Üyeler  
 `dwValidFields`  
 Hangi alanların başlatılmış belirtmek için kullanılan bir numaralandırılmış veri türü.  
  
 `bstrName`  
 Bir bağlam içinde özellik adı.  
  
 `bstrType`  
 Özellik biçimlendirilmiş bir dize olarak yazın.  
  
 `bstrValue`  
 Özellik değeri olarak biçimlendirilmiş bir dize.  
  
 `bstrFullName`  
 Özelliğin tam adı.  
  
 `dwAttrib`  
 Hata ayıklama özellik öznitelikleri bayrakları belirtir numaralandırması.  
  
 `pDebugProp`  
 `IDebugProperty`Buna karşılık gelen nesne `ExtendedDebugPropertyInfo`.  
  
 `nDISPID`  
 Dağıtım kimliği.  
  
 `nType`  
 Genişletilmiş özellik türü.  
  
 `varValue`  
 VARIANT sığabilecek, genişletilmiş özellik değeri.  
  
 `plbValue`  
 Özellik değeri gerçek veri bayt sayısı.  
  
 `pDebugExtProp`  
 `IDebugExtendedProperty`Buna karşılık gelen nesne `ExtendedDebugPropertyInfo`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Debugpropertyınfo yapısı](../../winscript/reference/debugpropertyinfo-structure.md)   
 [Idebugproperty arabirimi](../../winscript/reference/idebugproperty-interface.md)   
 [Idebugextendedproperty arabirimi](../../winscript/reference/idebugextendedproperty-interface.md)   
 [DBGPROP_ATTRIB_FLAGS](../../winscript/reference/dbgprop-attrib-flags.md)   
 [DBGPROP_INFO_FLAGS](../../winscript/reference/dbgprop-info-flags.md)