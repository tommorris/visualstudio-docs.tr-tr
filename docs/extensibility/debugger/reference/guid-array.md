---
title: GUID_ARRAY | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GUID_ARRAY structure
ms.assetid: 9e12500c-2c1c-49b1-a0ba-e08366c97eb8
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: b0273fd1d3ec54b8f142fb905701a5f6218ecb2b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="guidarray"></a>GUID_ARRAY
Kullanılabilir hata ayıklama altyapıları için benzersiz tanımlayıcı bir dizi açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct tagGUID_ARRAY  
{  
   DWORD dwCount;  
   GUID *Members;  
} GUID_ARRAY;  
```  
  
```csharp  
public struct GUID_ARRAY  
{  
   public uint dwCount;  
   public Guid Members;  
}  
```  
  
## <a name="terms"></a>Koşulları  
 dwCount  
 Dizideki benzersiz tanımlayıcıları sayısı.  
  
 Üyeler  
 Benzersiz tanımlayıcılar içeren bir dizi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı tarafından döndürülen [GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md)