---
title: GetScheduledTasksForDebugger yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- GetScheduledTasksForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 7c9b4cde-6e4a-4cef-929f-7d02b1da5762
caps.latest.revision: 10
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 1c27bd57684fc0a4de0bf56bcc8db9a5561f7d1f
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="getscheduledtasksfordebugger-method"></a>GetScheduledTasksForDebugger Method
Tüm zamanlanmış görevlerin dizisini alır.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Derleme:** mscorlib (içinde mscorlib.dll)  
  
 İç bu üye .NET Framework'teki erişemediği için aşağıdaki söz dizimini ortak Ara dile (CIL) sağlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
.method assembly hidebysig instance class System.Threading.Tasks.Task[] GetScheduledTasksForDebugger() cil managed  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Tüm zamanlanmış görevler dizisi. Her görev yürütüyor veya yürütülmesi tamamlandı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem iş parçacığı içinde korumalı değil ve diğer örnekleriyle aynı anda kullanılmamalıdır <xref:System.Threading.Tasks.TaskScheduler> yalnızca hata ayıklayıcı diğer tüm iş parçacıklarını askıya aldı olduğunda bu hata ayıklayıcı'dan çağrılmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [TaskScheduler sınıfı](../../extensibility/debugger/taskscheduler-class-internal-members.md)