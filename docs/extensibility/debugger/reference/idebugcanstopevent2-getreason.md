---
title: IDebugCanStopEvent2::GetReason | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCanStopEvent2::GetReason
helpviewer_keywords:
- IDebugCanStopEvent2::GetReason
ms.assetid: f5de31ca-7b8d-4029-9cf9-ba860ac66af6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4c0eaefee714467084898182b338ceda63ebdc0f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugcanstopevent2getreason"></a>IDebugCanStopEvent2::GetReason
Hata ayıklama altyapısı (DE) neden durdurmak istiyor nedenini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetReason(   
   CANSTOP_REASON* pcr  
);  
```  
  
```csharp  
int GetReason(   
   out enum_CANSTOP_REASON pcr  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pcr`  
 [out] Arasında bir değer döndürür [CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md) bu olay nedenini açıklayan numaralandırması.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem genellikle önce çağrılır [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md) böylece arayan mi sıfır geçirmek belirleyebilir yöntemi (`TRUE`) için `IDebugCanStopEvent2::CanStop` yöntemi.  
  
 Durdurma nedeni olabilir `CANSTOP_ENTRYPOINT`, DE başka bir deyişle, bir giriş noktası ulaştı veya `CANSTOP_STEPIN`, DE başka bir deyişle, bir işlevdeki kalkan.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)   
 [CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md)   
 [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)