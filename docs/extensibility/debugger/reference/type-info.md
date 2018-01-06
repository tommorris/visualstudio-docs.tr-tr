---
title: TYPE_INFO | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: TYPE_INFO
helpviewer_keywords: TYPE_INFO structure
ms.assetid: d725cb68-a565-49d1-a16f-ff0445c587a0
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0d6888d2680cffbde132885d730cd35f6e509c2e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="typeinfo"></a>TYPE_INFO
Bu yapı çeşitli bir alanın türü hakkındaki bilgileri belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
struct _tagTYPE_INFO_UNION {  
   dwTYPE_KIND dwKind;  
   union {  
      METADATA_TYPE typeMeta;  
      PDB_TYPE      typePdb;  
      BUILT_TYPE    typeBuilt;  
      DWORD         unused;  
   } type;  
} TYPE_INFO;  
```  
  
```csharp  
public struct TYPE_INFO {  
   public uint   dwKind;  
   public IntPtr unionmember;  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 dwKind  
 Arasında bir değer [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md) UNION yorumlama belirler numaralandırması.  
  
 type.typeMeta  
 [Yalnızca C++] İçeren bir [METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md) , yapı `dwKind` olan `TYPE_KIND_METADATA`.  
  
 type.typePdb  
 [Yalnızca C++] İçeren bir [PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md) , yapı `dwKind` olan `TYPE_KIND_PDB`.  
  
 type.typeBuilt  
 [Yalnızca C++] İçeren bir [BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md) , yapı `dwKind` olan `TYPE_KIND_BUILT`.  
  
 Type.Unused  
 Kullanılmayan doldurma.  
  
 türü  
 UNION adı.  
  
 unionmember  
 [Sadece C#] Bunun için uygun bir yapı türüne göre sıralama `dwKind`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı geçirilir [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md) yöntemi burada bunu doldurulur. Yapı içeriğini nasıl yorumlanacağını dayanır `dwKind` alan.  
  
> [!NOTE]
>  [Yalnızca C++] Varsa `dwKind` eşittir `TYPE_KIND_BUILT`, arka plandaki serbest bırakmak gerekli olan sonra [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) nesne yok etme işleminde `TYPE_INFO` yapısı. Bu çağırarak yapılır `typeInfo.type.typeBuilt.pUnderlyingField->Release()`.  
  
 [Sadece C#] Aşağıdaki tabloda yorumlama gösterilmektedir `unionmember` üyesi için her türde. Bu örnek, bu tür bir tür için nasıl yapıldığını gösterir.  
  
|`dwKind`|`unionmember`yorumlanan|  
|--------------|----------------------------------|  
|`TYPE_KIND_METADATA`|[METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md)|  
|`TYPE_KIND_PDB`|[PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md)|  
|`TYPE_KIND_BUILT`|[BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md)|  
  
## <a name="example"></a>Örnek  
 Bu örnek nasıl yorumlanacağını gösterir `unionmember` üyesi `TYPE_INFO` C# yapısı. Bu örnek, yalnızca bir tür yorumlama gösterir (`TYPE_KIND_METADATA`), ancak diğer tam olarak aynı şekilde yorumlanır.  
  
```csharp  
using System;  
using System.Runtime.Interop.Services;  
using Microsoft.VisualStudio.Debugger.Interop;  
  
namespace MyPackage  
{  
    public class MyClass  
    {  
        public void Interpret(TYPE_INFO ti)  
        {  
            if (ti.dwKind == (uint)enum_dwTypeKind.TYPE_KIND_METADATA)  
            {  
                 METADATA_TYPE dataType = (METADATA_TYPE)Marshal.PtrToStructure(ti.unionmember,  
                                               typeof(METADATA_TYPE));  
            }  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)   
 [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md)   
 [METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md)   
 [PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md)   
 [BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md)