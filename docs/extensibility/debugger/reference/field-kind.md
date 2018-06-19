---
title: FIELD_KIND | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- FIELD_KIND
helpviewer_keywords:
- FIELD_KIND enumeration
ms.assetid: fd522b9c-52e2-42fa-939d-343347d5c3b1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 35a603310986f42141a04f38c7ce26db0d7326fe
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31109668"
---
# <a name="fieldkind"></a>FIELD_KIND
İçinde yer alan türünü belirtir bir [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_FIELD_KIND {   
   FIELD_KIND_NONE       = 0x00000000,  
  
   // Type of field  
   FIELD_KIND_TYPE       = 0x00000001,  
   FIELD_KIND_SYMBOL     = 0x00000002,  
  
   // Storage type of the field  
   FIELD_TYPE_PRIMITIVE  = 0x00000010,  
   FIELD_TYPE_STRUCT     = 0x00000020,  
   FIELD_TYPE_CLASS      = 0x00000040,  
   FIELD_TYPE_INTERFACE  = 0x00000080,  
   FIELD_TYPE_UNION      = 0x00000100,  
   FIELD_TYPE_ARRAY      = 0x00000200,  
   FIELD_TYPE_METHOD     = 0x00000400,  
   FIELD_TYPE_BLOCK      = 0x00000800,  
   FIELD_TYPE_POINTER    = 0x00001000,  
   FIELD_TYPE_ENUM       = 0x00002000,  
   FIELD_TYPE_LABEL      = 0x00004000,  
   FIELD_TYPE_TYPEDEF    = 0x00008000,  
   FIELD_TYPE_BITFIELD   = 0x00010000,  
   FIELD_TYPE_NAMESPACE  = 0x00020000,  
   FIELD_TYPE_MODULE     = 0x00040000,  
   FIELD_TYPE_DYNAMIC    = 0x00080000,  
   FIELD_TYPE_PROP       = 0x00100000,  
   FIELD_TYPE_INNERCLASS = 0x00200000,  
   FIELD_TYPE_REFERENCE  = 0x00400000,  
   FIELD_TYPE_EXTENDED   = 0x00800000,  
  
   // Specific information about symbols  
   FIELD_SYM_MEMBER      = 0x01000000,  
   FIELD_SYM_LOCAL       = 0x02000000,  
   FIELD_SYM_PARAM       = 0x04000000,  
   FIELD_SYM_THIS        = 0x08000000,  
   FIELD_SYM_GLOBAL      = 0x10000000,  
   FIELD_SYM_PROP_GETTER = 0x20000000,  
   FIELD_SYM_PROP_SETTER = 0x40000000,  
   FIELD_SYM_EXTENDED    = 0x80000000,  
  
   FIELD_KIND_MASK       = 0x0000000f,  
   FIELD_TYPE_MASK       = 0x00fffff0,  
   FIELD_SYM_MASK        = 0xff000000,  
  
   FIELD_KIND_ALL        = 0xffffffff  
};  
typedef DWORD FIELD_KIND;  
```  
  
```csharp  
public enum enum_FIELD_KIND {  
   FIELD_KIND_NONE       = 0x00000000,  
  
   // Type of field  
   FIELD_KIND_TYPE       = 0x00000001,  
   FIELD_KIND_SYMBOL     = 0x00000002,  
  
   // Storage type of the field  
   FIELD_TYPE_PRIMITIVE  = 0x00000010,  
   FIELD_TYPE_STRUCT     = 0x00000020,  
   FIELD_TYPE_CLASS      = 0x00000040,  
   FIELD_TYPE_INTERFACE  = 0x00000080,  
   FIELD_TYPE_UNION      = 0x00000100,  
   FIELD_TYPE_ARRAY      = 0x00000200,  
   FIELD_TYPE_METHOD     = 0x00000400,  
   FIELD_TYPE_BLOCK      = 0x00000800,  
   FIELD_TYPE_POINTER    = 0x00001000,  
   FIELD_TYPE_ENUM       = 0x00002000,  
   FIELD_TYPE_LABEL      = 0x00004000,  
   FIELD_TYPE_TYPEDEF    = 0x00008000,  
   FIELD_TYPE_BITFIELD   = 0x00010000,  
   FIELD_TYPE_NAMESPACE  = 0x00020000,  
   FIELD_TYPE_MODULE     = 0x00040000,  
   FIELD_TYPE_DYNAMIC    = 0x00080000,  
   FIELD_TYPE_PROP       = 0x00100000,  
   FIELD_TYPE_INNERCLASS = 0x00200000,  
   FIELD_TYPE_REFERENCE  = 0x00400000,  
   FIELD_TYPE_EXTENDED   = 0x00800000,  
  
   // Specific information about symbols  
   FIELD_SYM_MEMBER      = 0x01000000,  
   FIELD_SYM_LOCAL       = 0x02000000,  
   FIELD_SYM_PARAM       = 0x04000000,  
   FIELD_SYM_THIS        = 0x08000000,  
   FIELD_SYM_GLOBAL      = 0x10000000,  
   FIELD_SYM_PROP_GETTER = 0x20000000,  
   FIELD_SYM_PROP_SETTER = 0x40000000,  
   FIELD_SYM_EXTENDED    = 0x80000000,  
  
   FIELD_KIND_MASK       = 0x0000000f,  
   FIELD_TYPE_MASK       = 0x00fffff0,  
   FIELD_SYM_MASK        = 0xff000000,  
  
   FIELD_KIND_ALL        = 0xffffffff  
};  
```  
  
## <a name="members"></a>Üyeler  
 FIELD_KIND_TYPE  
 Alan yalnızca bir türü olduğunu gösterir.  
  
 FIELD_KIND_SYMBOL  
 Alan türü, adı ve diğer bilgileri ile bir simge olduğunu gösterir.  
  
 FIELD_TYPE_PRIMITIVE  
 Alan bir temel veri türü olduğunu gösterir.  
  
 FIELD_TYPE_STRUCT  
 Alan bir yapı gösterir.  
  
 FIELD_TYPE_CLASS  
 Alanın bir sınıf olduğunu belirtir.  
  
 FIELD_TYPE_INTERFACE  
 Alan bir arabirim olduğunu gösterir.  
  
 FIELD_TYPE_UNION  
 Alan bir birleşim olduğunu gösterir.  
  
 FIELD_TYPE_ARRAY  
 Alan bir dizi olduğunu gösterir.  
  
 FIELD_TYPE_METHOD  
 Alan bir yöntemi gösterir.  
  
 FIELD_TYPE_BLOCK  
 Alan bir bloğu gösterir.  
  
 FIELD_TYPE_POINTER  
 Alan bir işaretçi olduğunu gösterir.  
  
 FIELD_TYPE_ENUM  
 Alan numaralandırılmış veri türü olduğunu gösterir.  
  
 FIELD_TYPE_LABEL  
 Alan bir etiket olduğunu gösterir.  
  
 FIELD_TYPE_TYPEDEF  
 Alan bir typedef olduğunu gösterir.  
  
 FIELD_TYPE_BITFIELD  
 Alan bir saklayıcısında olduğunu gösterir.  
  
 FIELD_TYPE_NAMESPACE  
 Alan bir ad alanı olduğunu gösterir.  
  
 FIELD_TYPE_MODULE  
 Alan bir modül olduğunu gösterir.  
  
 FIELD_TYPE_DYNAMIC  
 Alan dinamik olduğunu gösterir.  
  
 FIELD_TYPE_PROP  
 Alan bir özellik olduğunu gösterir.  
  
 FIELD_TYPE_INNERCLASS  
 Alan bir iç sınıf olduğunu gösterir.  
  
 FIELD_TYPE_REFERENCE  
 Alan bir başvuru olduğunu gösterir.  
  
 FIELD_TYPE_EXTENDED  
 Daha sonraki kullanımlar için ayrılmıştır.  
  
 FIELD_SYM_MEMBER  
 Alanın üyesi olduğunu gösterir.  
  
 FIELD_SYM_LOCAL  
 Alan yerel olduğunu gösterir.  
  
 FIELD_SYM_PARAMETER  
 Alan bir parametre olduğunu gösterir.  
  
 FIELD_SYM_THIS  
 Alan "Bu" işaretçiyi olduğunu gösterir.  
  
 FIELD_SYM_GLOBAL  
 Alan genel olduğunu gösterir.  
  
 FIELD_SYM_PROP_GETTER  
 Alan özelliklerini alır gösterir.  
  
 FIELD_SYM_PROP_SETTER  
 Alan özellikleri oluşturduğunu gösterir.  
  
 FIELD_SYM_EXTENDED  
 Daha sonraki kullanımlar için ayrılmıştır.  
  
 FIELD_KIND_MASK  
 Alan türleri için maskesi gösterir.  
  
 FIELD_TYPE_MASK  
 Alan türleri için maskesi gösterir.  
  
 FIELD_SYM_MASK  
 Sembol bilgileri için bir maskesi gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrısından döndürülen [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) yöntemi.  
  
 Bu alanın türünü bağlı olarak [QueryInterface](/cpp/atl/queryinterface) çağrılabilir [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) arabiriminin daha belirli bir form için arabirim. Örneğin, varsa [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) döndürür `FIELD_TYPE_METHOD`, ardından çağırabilirsiniz `QueryInterface` ı üzerinde`DebugField` almak için [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md) arabirimi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md)   
 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)