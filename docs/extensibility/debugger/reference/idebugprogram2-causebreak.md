---
title: IDebugProgram2::CauseBreak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::CauseBreak
helpviewer_keywords:
- IDebugProgram2::CauseBreak
ms.assetid: 07d353fc-68ab-4297-a18f-3d3c7a80e121
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 81fb04db3342bb8ce7d5e314c9a912b873ffb627
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogram2causebreak"></a>IDebugProgram2::CauseBreak
Program yürütme sonraki durdurma isteği çalıştırmak için iş parçacığı girişimlerinin birini zaman.  
  
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
 Bir [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) program sonraki bu yöntemi çağırıldıktan sonra kod çalıştırmayı denediğinde, olay gönderilir.  
  
 Programı durdurmak için mutlaka beklemeden yöntemi hemen döndürür, bu zaman uyumsuz bir yöntemdir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)