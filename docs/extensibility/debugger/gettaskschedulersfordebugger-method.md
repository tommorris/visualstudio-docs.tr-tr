---
title: GetTaskSchedulersForDebugger yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- GetTaskSchedulersForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 58aa236a-5ab8-4695-b303-89dffdbcd946
caps.latest.revision: 10
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a2c657b7cef89871e17af442e41229c2fda0f4b7
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="gettaskschedulersfordebugger-method"></a>GetTaskSchedulersForDebugger Method
Tüm dizisini alır <xref:System.Threading.Tasks.TaskScheduler> şu an etkin olan nesneleri.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Derleme:** mscorlib (içinde mscorlib.dll)  
  
 İç bu üye .NET Framework'teki erişemediği için aşağıdaki söz dizimini ortak Ara dile (CIL) sağlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
.method assembly hidebysig static class System.Threading.Tasks.TaskScheduler[] GetTaskSchedulersForDebugger() cil managed  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Tüm bir dizi <xref:System.Threading.Tasks.TaskScheduler> bu şu anda etkin olan nesneler <xref:System.AppDomain>.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem iş parçacığı içinde korumalı değil ve diğer örnekleriyle aynı anda kullanılmamalıdır <xref:System.Threading.Tasks.TaskScheduler>. Hata ayıklayıcı diğer tüm iş parçacıklarının yalnızca duraklattı olduğunda hata ayıklayıcı'dan çağrılmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [TaskScheduler sınıfı](../../extensibility/debugger/taskscheduler-class-internal-members.md)