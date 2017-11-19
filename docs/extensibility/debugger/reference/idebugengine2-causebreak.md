---
title: IDebugEngine2::CauseBreak | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngine2::CauseBreak
helpviewer_keywords: IDebugEngine2::CauseBreak
ms.assetid: 17fe4698-b04e-4798-8412-80e0da60c387
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: eeb8c262d6e1abc88e40f027d921ae2d4ae12cf2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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