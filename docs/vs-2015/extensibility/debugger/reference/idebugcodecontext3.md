---
title: IDebugCodeContext3 | Microsoft Docs
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
- IDebugCodeContext3 interface
ms.assetid: 524eb882-0ad5-4bfb-95eb-eb3abb3d0237
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7064cddbf81a01e7d55d64249d4ff4da6e585728
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695135"
---
# <a name="idebugcodecontext3"></a>IDebugCodeContext3
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugCodeContext3](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcodecontext3).  
  
Genişletir [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) modülü ve işlem arabirimleri alınmasını etkinleştirmek için arabirim.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugCodeContext3 : IDebugCodeContext2  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama motoru tarafından uygulanan ve tarafından tüketilen [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] paketinin hatalarını ayıkla.  
  
## <a name="methods"></a>Yöntemler  
 Yöntemlere ek olarak `IDebugCodeContext2` arabirimi bu arabirim, aşağıdaki yöntemleri uygular:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetModule](../../../extensibility/debugger/reference/idebugcodecontext3-getmodule.md)|Hata ayıklama modülü arabirimine bir başvuru alır.|  
|[GetProcess](../../../extensibility/debugger/reference/idebugcodecontext3-getprocess.md)|Hata ayıklama işlemini arabirimine bir başvuru alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu genellikle uygulanacak bulunmayan isteğe bağlı bir arabirimdir.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll

