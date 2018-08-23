---
title: GUID_ARRAY | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- GUID_ARRAY structure
ms.assetid: 9e12500c-2c1c-49b1-a0ba-e08366c97eb8
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c4540cb45b9a80d1a0a643554b9f25c02b88570c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695383"
---
# <a name="guidarray"></a>GUID_ARRAY
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [GUID_ARRAY](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/guid-array).  
  
Bir dizi benzersiz tanımlayıcıları kullanılabilir hata ayıklama altyapıları için açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 Dizide benzersiz tanımlayıcıları sayısı.  
  
 Üyeler  
 Benzersiz tanımlayıcıları içeren bir dizi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı tarafından döndürülen [GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimler](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md)

