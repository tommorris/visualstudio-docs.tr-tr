---
title: DEBUG_ADDRESS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DEBUG_ADDRESS
helpviewer_keywords:
- DEBUG_ADDRESS structure
ms.assetid: 79f5e765-9aac-4b6e-82ef-bed88095e9ba
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 07312208967aeccfbd81f44587f84a43dfebf4c0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31101452"
---
# <a name="debugaddress"></a>DEBUG_ADDRESS
Bu yapı bir adresi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct _tagDEBUG_ADDRESS {  
   ULONG32             ulAppDomainID;  
   GUID                guidModule;  
   _mdToken            tokClass;  
   DEBUG_ADDRESS_UNION addr;  
} DEBUG_ADDRESS;  
```  
  
```csharp  
public struct DEBUG_ADDRESS {  
   public uint                ulAppDomainID;  
   public Guid                guidModule;  
   public int                 tokClass;  
   public DEBUG_ADDRESS_UNION addr;  
}  
```  
  
## <a name="terms"></a>Koşulları  
 ulAppDomainID  
 İşlem kimliği.  
  
 guidModule  
 Bu adres içeren modülü GUID.  
  
 tokClass  
 Sınıf veya bu adres türünü tanımlayan belirteci.  
  
> [!NOTE]
>  Bu değer bir simge sağlayıcıya özeldir ve bu nedenle bir sınıf türü için bir tanımlayıcı olarak dışında genel anlamı yoktur.  
  
 Adr  
 A [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) tek tek adres türlerini açıklayan yapıları birleşimini içerir yapısı. Değer `addr`.`dwKind` geldiği [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) UNION yorumlama açıklar numaralandırması.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı geçirilir [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md) doldurulacak yöntemi.  
  
 **Uyarı [yalnızca C++]**  
  
 Varsa `addr.dwKind` olan `ADDRESS_KIND_METADATA_LOCAL` ve `addr.addr.addrLocal.pLocal` çağırmalısınız sonra boş bir değer değil `Release` belirteci işaretçi üzerinde:  
  
```  
if (addr.dwKind == ADDRESS_KIND_METADATA_LOCAL &&  addr.addr.addrLocal.pLocal != NULL)  
{  
    addr.addr.addrLocal.pLocal->Release();  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)