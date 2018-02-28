---
title: IDebugBoundBreakpoint2::GetHitCount | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugBoundBreakpoint2::GetHitCount
helpviewer_keywords:
- GetHitCount method
- IDebugBoundBreakpoint2::GetHitCount method
ms.assetid: 23481f37-047c-41d2-8286-4da1f4084961
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a955c56eb8b3705dd967e2c070ce140abe930043
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugboundbreakpoint2gethitcount"></a>IDebugBoundBreakpoint2::GetHitCount
Geçerli isabet sayısı için ilişkili bu kesme noktası alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetHitCount(   
   DWORD* pdwHitCount  
);  
```  
  
```csharp  
int GetHitCount(   
   out uint pdwHitCount  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pdwHitCount`  
 [out] İsabet sayımını döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Döndürür `E_BP_DELETED` ilişkili kesme noktası nesnenin durumu ayarlanırsa `BPS_DELETED` (parçası [BP_STATE](../../../extensibility/debugger/reference/bp-state.md) numaralandırması).  
  
## <a name="remarks"></a>Açıklamalar  
 İsabet sayısı bu kesme oturumun geçerli çalışması sırasında harekete sayısıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)