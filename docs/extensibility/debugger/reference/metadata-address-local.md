---
title: METADATA_ADDRESS_LOCAL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- METADATA_ADDRESS_LOCAL
helpviewer_keywords:
- METADATA_ADDRESS_LOCAL structure
ms.assetid: 635f6bc5-c486-4e0e-83db-36f15e543843
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 74d59fb19d130ad53ddbf200e96cdf04e958e239
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="metadataaddresslocal"></a>METADATA_ADDRESS_LOCAL
Bu yapı (genellikle bir işlev veya yöntem) kapsam içinde yerel değişkenin adresini temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct _tagMETADATA_ADDRESS_LOCAL {  
   _mdToken  tokMethod;  
   IUnknown* pLocal;  
   DWORD     dwIndex;  
} METADATA_ADDRESS_LOCAL;  
```  
  
```csharp  
public struct METADATA_ADDRESS_LOCAL {  
   public int    tokMethod;  
   public object pLocal;  
   public uint   dwIndex;  
}  
```  
  
## <a name="terms"></a>Koşulları  
 tokMethod  
 Yöntemi veya işlev Kimliğini yerel değişken parçası değildir.  
  
 [C++] `_mdToken` olan bir `typedef` 32 bit `int`.  
  
 pLocal  
 Belirteç adresi bu yapıyı temsil eder.  
  
 dwIndex  
 Bu yöntemi veya işlev ya da başka bir değer (dile özgü) yerel değişkeni dizin olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı birleşim içinde yer [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) ne zaman yapısı `dwKind` alanını `DEBUG_ADDRESS_UNION` yapısı ayarlanmış `ADDRESS_KIND_LOCAL` (arasında bir değer [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) numaralandırma).  
  
 `Warning:`[Yalnızca C++]  Varsa `pLocal` null değil çağırmalısınız sonra `Release` belirteci işaretçi üzerinde (`addr` bir alandır [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) yapısı):  
  
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
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)