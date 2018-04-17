---
title: DEBUG_REFERENCE_INFO | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DEBUG_REFERENCE_INFO
helpviewer_keywords:
- DEBUG_REFERENCE_INFO structure
ms.assetid: 24b83d00-d756-42a1-8083-730f998761dc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a528f73f0a13ab2702e35212a3ba00f8c8c13378
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="debugreferenceinfo"></a>DEBUG_REFERENCE_INFO
Bir başvuru açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct tagDEBUG_REFERENCE_INFO {   
   DEBUGREF_INFO_FLAGS dwFields;  
   BSTR                bstrName;  
   BSTR                bstrType;  
   BSTR                bstrValue;  
   DBG_ATTRIB_FLAGS    dwAttrib;  
   REFERENCE_TYPE.     dwRefType;  
   IDebugReference2*   m_pReference;  
} DEBUG_REFERENCE_INFO;  
```  
  
```csharp  
public struct DEBUG_REFERENCE_INFO {   
   public uint             dwFields;  
   public string           bstrName;  
   public string           bstrType;  
   public string           bstrValue;  
   public ulong            dwAttrib;  
   public uint.            dwRefType;  
   public IDebugReference2 m_pReference;  
};  
```  
  
## <a name="members"></a>Üyeler  
 dwFields  
 Bayraklarını bileşimini [DEBUGREF_INFO_FLAGS](../../../extensibility/debugger/reference/debugref-info-flags.md) hangi alanların doldurulmuş belirtir numaralandırması.  
  
 bstrName  
 Kullanıcı tanımlı adı [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) nesnesi.  
  
 bstrType  
 Başvuru türü olarak biçimlendirilmiş bir dize.  
  
 bstrValue  
 Biçimlendirilmiş bir dize olarak başvuru değeri  
  
 dwAttrib  
 Bayraklarını bileşimini [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) hata ayıklama özellik öznitelikleri bayrakları belirtir numaralandırması.  
  
 dwRefType  
 Arasında bir değer [REFERENCE_TYPE](../../../extensibility/debugger/reference/reference-type.md) başvuru türü güçlü veya zayıf olduğunu belirten numaralandırma.  
  
 m_pReference  
 Bir [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) nesne başvuru bilgileri belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı için bir çağrı geçirilir [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md) doldurulacak yöntemi. Bu yapı listeden bir parçası olarak da döndürülür [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md) hangi sırayla çağrısından döndürülen arabirimi [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [DEBUGREF_INFO_FLAGS](../../../extensibility/debugger/reference/debugref-info-flags.md)   
 [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)   
 [REFERENCE_TYPE](../../../extensibility/debugger/reference/reference-type.md)   
 [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)   
 [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md)