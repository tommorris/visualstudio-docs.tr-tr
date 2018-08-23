---
title: IDebugPendingBreakpoint2::SetCondition | Microsoft Docs
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
- IDebugPendingBreakpoint2::SetCondition
helpviewer_keywords:
- SetCondition method
- IDebugPendingBreakpoint2::SetCondition method
ms.assetid: 0534224f-654f-4862-bc4d-a9a81a5f8899
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 483b0a4101d173c6f5e6aa55a525276d3e8c1732
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693860"
---
# <a name="idebugpendingbreakpoint2setcondition"></a>IDebugPendingBreakpoint2::SetCondition
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugPendingBreakpoint2::SetCondition](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugpendingbreakpoint2-setcondition).  
  
Bekleyen kesme noktasıyla ilişkilendirilmiş olan koşul değiştirir veya ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT SetCondition(   
   BP_CONDITION bpCondition  
);  
```  
  
```csharp  
int SetCondition(   
   BP_CONDITION bpCondition  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `bpCondition`  
 [in] A [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) ayarlamak için koşul belirtir yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Daha önce bekleyen kesme noktasıyla ilgili herhangi bir koşul kaybolur. Bu Kesme noktasının bağlı tüm kesme noktalarını, koşul içinde belirtilen değere ayarlamak için çağrılır `bpCondition` parametresi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)

