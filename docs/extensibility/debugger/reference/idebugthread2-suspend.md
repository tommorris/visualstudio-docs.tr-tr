---
title: IDebugThread2::Suspend | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugThread2::Suspend
helpviewer_keywords:
- IDebugThread2::Suspend
ms.assetid: 1e20be85-aa12-48de-bb83-0bf0976e99ae
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f865194e023ed0311f06988dd026fb2b123aaf4a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugthread2suspend"></a>IDebugThread2::Suspend
Bir iş parçacığı askıya alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Suspend (   
   DWORD *pdwSuspendCount  
);  
```  
  
```csharp  
HRESULT Suspend (   
   out uint pdwSuspendCount  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pdwSuspendCount`  
 [out] Askıya alma sayımı askıya alma işleminden sonra döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem her çağrı 0 yukarıda askıya alma sayısını artırır. Bu askıya alma sayımı görüntülenen **iş parçacığı** hata ayıklama penceresi.  
  
 Bu yöntem her çağrı için koyulmalıdır sonraki çağrı [Sürdür](../../../extensibility/debugger/reference/idebugthread2-resume.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Devam et](../../../extensibility/debugger/reference/idebugthread2-resume.md)