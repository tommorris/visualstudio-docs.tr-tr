---
title: IDebugBoundBreakpoint2::SetHitCount | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugBoundBreakpoint2::SetHitCount
helpviewer_keywords:
- SetHitCount method
- IDebugBoundBreakpoint2::SetHitCount method
ms.assetid: 8145d875-26b1-4049-a2a2-e7d3d7f4735f
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 44393469852cc17c982e644433ba8f38af5f7aa1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugboundbreakpoint2sethitcount"></a>IDebugBoundBreakpoint2::SetHitCount
İlişkili kesme noktası isabet sayısı ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT SetHitCount(   
   DWORD dwHitCount  
);  
```  
  
```csharp  
int SetHitCount(   
   uint dwHitCount  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwHitCount`  
 [in] Ayarlanacak isabet sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Döndürür `E_BP_DELETED` ilişkili kesme noktası nesnenin durumu ayarlanırsa `BPS_DELETED` (parçası [BP_STATE](../../../extensibility/debugger/reference/bp-state.md) numaralandırması).  
  
## <a name="remarks"></a>Açıklamalar  
 İsabet sayısı bu kesme oturumun geçerli çalışması sırasında harekete sayısıdır.  
  
 Bu yöntem, genellikle bu kesme geçerli isabet sayısına güncelleştirmek için hata ayıklama altyapısı tarafından çağrılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)