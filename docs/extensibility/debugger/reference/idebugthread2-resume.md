---
title: IDebugThread2::Resume | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugThread2::Resume
helpviewer_keywords: IDebugThread2::Resume
ms.assetid: 36aad682-b0b9-40a2-b3fc-f0e61d41cdbc
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5de844c3b07a509f266e2f9d278d1f78bea2b089
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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