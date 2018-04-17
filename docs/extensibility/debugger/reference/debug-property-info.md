---
title: DEBUG_PROPERTY_INFO | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DEBUG_PROPERTY_INFO
helpviewer_keywords:
- DEBUG_PROPERTY_INFO structure
ms.assetid: 5a085d18-62c6-4740-b9e9-3f5db6bfdf7f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4466d74d0e19b898b3c377c67a14f7c39922d915
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="debugpropertyinfo"></a>DEBUG_PROPERTY_INFO
Hata ayıklama özelliği hakkında bilgiler içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct tagDEBUG_PROPERTY_INFO {   
   DEBUGPROP_INFO_FLAGS dwValidFields;  
   BSTR                 bstrFullName;  
   BSTR                 bstrName;  
   BSTR                 bstrType;  
   BSTR                 bstrValue;  
   IDebugProperty2*     pProperty;  
   DBG_ATTRIB_FLAGS     dwAttrib;  
} DEBUG_PROPERTY_INFO;  
```  
  
```csharp  
public struct DEBUG_PROPERTY_INFO {   
   public uint            dwValidFields;  
   public string          bstrFullName;  
   public string          bstrName;  
   public string          bstrType;  
   public string          bstrValue;  
   public IDebugProperty2 pProperty;  
   public ulong           dwAttrib;  
};  
```  
  
## <a name="members"></a>Üyeler  
 dwValidFields  
 Bayraklarını bileşimini [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) hangi alanların doldurulur belirtir numaralandırması.  
  
 bstrFullName  
 Özelliğin tam adı.  
  
 bstrName  
 Bir bağlam içinde özellik adı.  
  
 bstrType  
 Özellik türü olarak biçimlendirilmiş bir dize.  
  
 bstrValue  
 Özellik değeri olarak biçimlendirilmiş bir dize.  
  
 pProperty  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) bu yapısı tarafından tanımlanan nesnesi.  
  
 dwAttrib  
 Bayraklarını bileşimini [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) bu özellik özniteliklerini açıklayan numaralandırması.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir nesnenin adı, türü ve değeri içeren hiyerarşik bir yapı özelliğidir. Örneğin, bir özelliği yerel değişkenler, parametreleri, izleme değişkenleri ve ifadeler ve kayıtları açıklayabilirsiniz.  
  
 Bu yapı geçirilir [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) yöntemi burada bunu doldurulur. Bu yapı bu yapısından listesinin bir parçası olarak da döndürülür [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) hangi sırayla çağrısından döndürülen arabirimi [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) ve [ EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md) yöntemleri.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)   
 [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)   
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)   
 [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)