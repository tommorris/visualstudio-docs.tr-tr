---
title: IDebugThread2::Resume | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugThread2::Resume
helpviewer_keywords:
- IDebugThread2::Resume
ms.assetid: 36aad682-b0b9-40a2-b3fc-f0e61d41cdbc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7f51fdb05fb44a23227a1a35fd6504f2d18aa804
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31121423"
---
# <a name="idebugthread2resume"></a>IDebugThread2::Resume
Bir iş parçacığı yürütülmesi sürdürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Resume (   
   DWORD *pdwSuspendCount  
);  
```  
  
```csharp  
int Resume (   
   out uint pdwSuspendCount  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pdwSuspendCount`  
 [out] Askıya alma sayımı sonra sürdürme işlemi döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Askıya alma sayısı her çağrı için bu yöntemi azaltır aynı zamanda 0 ulaşana kadar yürütülmesi gerçekte sürdürüldü. Bu askıya alma sayımı görüntülenen **iş parçacığı** hata ayıklama penceresi.  
  
 Bu yöntem her çağrı için koyulmalıdır önceki çağrısı [askıya alma](../../../extensibility/debugger/reference/idebugthread2-suspend.md) yöntemi. Askıya alma sayımı kaç kez belirler `IDebugThread2::Suspend` yönteminin çağrılıp çağrılmadığını kadarki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Askıya alma](../../../extensibility/debugger/reference/idebugthread2-suspend.md)