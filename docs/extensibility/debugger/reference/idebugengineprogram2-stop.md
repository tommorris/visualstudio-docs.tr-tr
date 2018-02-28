---
title: IDebugEngineProgram2::Stop | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugEngineProgram2::Stop
helpviewer_keywords:
- IDebugEngineProgram2::Stop
ms.assetid: 6e1c3d56-fb67-4a5b-80f9-8ee5131972bf
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 4004ca92b32e63565a71a3a6971ebb4ae073b9f9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugengineprogram2stop"></a>IDebugEngineProgram2::Stop
Tüm iş parçacıklarını bu programı çalıştırmayı durdurur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Stop(   
   void   
);  
```  
  
```csharp  
int Stop();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu program bir çok program ortamında ayıklanacak olduğunda bu yöntem çağrılır. Başka bir programı durdurma olayından alındığında, bu programı, bu yöntem çağrılır. Bu yöntemin kullanımı zaman uyumsuz olmalıdır; diğer bir deyişle, tüm iş parçacıklarının bu yöntem döndürmeden önce durdurulması gerekir. Bu yöntemin kullanımı çağırmak kadar kolaydır [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md) Bu program yöntemi.  
  
 Hata ayıklama olay yanıt bu yöntem olarak gönderilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)