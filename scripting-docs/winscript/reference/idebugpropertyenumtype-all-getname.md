---
title: IDebugPropertyEnumType_All::GetName | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugPropertyEnumType_All.GetName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugPropertyEnumType_All::GetName
ms.assetid: 24bbe4d5-4263-48d0-8e8d-bff957ffcad2
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 49b90938630fa96ca91f3346a37a7147ec2b90e7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24794327"
---
# <a name="idebugpropertyenumtypeallgetname"></a>IDebugPropertyEnumType_All::GetName
Adını içeren bir BSTR döndürür `EnumType`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetName(  
   BSTR*  pname  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pname`  
 [out] Adını içeren bir BSTR `EnumType`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir döndürür `HRESULT`, genellikle `S_OK`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idebugpropertyenumtype_all arabirimi](../../winscript/reference/idebugpropertyenumtype-all-interface.md)