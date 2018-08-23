---
title: IDebugThread2::Suspend | Microsoft Docs
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
- IDebugThread2::Suspend
helpviewer_keywords:
- IDebugThread2::Suspend
ms.assetid: 1e20be85-aa12-48de-bb83-0bf0976e99ae
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8bd4f45328b17c91c4525cb7fecb542961de5351
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688519"
---
# <a name="idebugthread2suspend"></a>IDebugThread2::Suspend
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugThread2::Suspend](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugthread2-suspend).  
  
Bir iş parçacığını askıya alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 [out] Askıya alma işleminden sonra askıya alma sayımı döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem her çağrı, askıya alma sayımı 0 yukarıda artırır. Bu askıya alma sayımı görüntülenir **iş parçacıkları** hata ayıklama penceresine.  
  
 Bu yöntem her çağrı için olmalıdır bir sonraki çağrı [sürdürme](../../../extensibility/debugger/reference/idebugthread2-resume.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Sürdür](../../../extensibility/debugger/reference/idebugthread2-resume.md)

