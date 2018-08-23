---
title: STEPKIND | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- STEPKIND
helpviewer_keywords:
- STEPKIND enumeration
ms.assetid: d3d8cf76-24bf-455e-803e-0e3e28f0b262
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e8d07f3d77d1f5f2c5deb8fcec75c6f4fac1fdf0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691462"
---
# <a name="stepkind"></a>STEPKIND
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [STEPKIND](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/stepkind).  
  
Adımı atlamak için belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
enum enum_STEPKIND {   
   STEP_INTO      = 0,  
   STEP_OVER      = 1,  
   STEP_OUT       = 2,  
   STEP_BACKWARDS = 3  
};  
typedef DWORD STEPKIND;  
```  
  
```csharp  
public enum enum_STEPKIND {   
   STEP_INTO      = 0,  
   STEP_OVER      = 1,  
   STEP_OUT       = 2,  
   STEP_BACKWARDS = 3  
};  
```  
  
## <a name="members"></a>Üyeler  
 STEP_INTO  
 Bir işlevi adımlar.  
  
 STEP_OVER  
 Bir işlevin üzerinden adımları.  
  
 STEP_OUT  
 Bir işlev dışında adımları.  
  
 STEP_BACKWARDS  
 Adımlamayla geriye dönük bir işlev.  
  
## <a name="remarks"></a>Açıklamalar  
 Bağımsız değişken olarak geçirilen [adım](../../../extensibility/debugger/reference/idebugprocess3-step.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Adım](../../../extensibility/debugger/reference/idebugprocess3-step.md)

