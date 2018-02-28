---
title: IDebugEngine2::CauseBreak | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugEngine2::CauseBreak
helpviewer_keywords:
- IDebugEngine2::CauseBreak
ms.assetid: 17fe4698-b04e-4798-8412-80e0da60c387
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c6fc6558ded5ab68f54170c07e2482ab2357475b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugengine2causebreak"></a>IDebugEngine2::CauseBreak
Tüm programları bu hata ayıklama altyapısı yürütme sonraki durdurmak için (DE) ayıklanacak istekleri kendi iş parçacığı birini çalıştırmayı dener.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT CauseBreak(   
   void   
);  
```  
  
```csharp  
int CauseBreak();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu zaman uyumsuz bir yöntemdir: bir [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) program sonraki bu yöntemi çağırıldıktan sonra yürütmeyi denediğinde olay gönderilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)