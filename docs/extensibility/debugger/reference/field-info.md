---
title: FIELD_INFO | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- FIELD_INFO
helpviewer_keywords:
- FIELD_INFO structure
ms.assetid: bfafef6d-0c83-43d7-a779-1f0d24b166a1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 180a968f642b8a4bf26e2e69d1d3ddff45dc1f25
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="fieldinfo"></a>FIELD_INFO
Bu yapı, yerel bir değişken, parametre veya diğer alan açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct _tagFieldInfo {   
   FIELD_INFO_FIELDS dwFields;  
   BSTR              bstrFullName;  
   BSTR              bstrName;  
   BSTR              bstrType;  
   FIELD_MODIFIERS   dwModifiers;  
} FIELD_INFO;  
```  
  
```csharp  
public struct FIELD_INFO {  
   public uint   dwFields;  
   public string bstrFullName;  
   public string bstrName;  
   public string bstrType;  
   public uint   dwModifiers;  
};  
```  
  
## <a name="members"></a>Üyeler  
 dwFields  
 Bayraklarını bileşimini [FIELD_INFO_FIELDS](../../../extensibility/debugger/reference/field-info-fields.md) olan üyeleri doldurulur belirtir numaralandırması.  
  
 bstrFullName  
 Alanının tam adı.  
  
 bstrName  
 Alan kısa adı.  
  
 bstrType  
 Alanın türü.  
  
 dwModifiers  
 Bayraklarını bileşimini [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md) alan açıklar numaralandırması.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı geçirilir [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md) yöntemi burada bunu doldurulur.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [FIELD_INFO_FIELDS](../../../extensibility/debugger/reference/field-info-fields.md)   
 [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)