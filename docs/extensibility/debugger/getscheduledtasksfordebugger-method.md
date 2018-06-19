---
title: GetScheduledTasksForDebugger yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- GetScheduledTasksForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 7c9b4cde-6e4a-4cef-929f-7d02b1da5762
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 20cde88083acd38df780468927faec5fbd142b67
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31100318"
---
# <a name="getscheduledtasksfordebugger-method"></a>GetScheduledTasksForDebugger yöntemi
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