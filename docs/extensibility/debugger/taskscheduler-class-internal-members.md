---
title: TaskScheduler sınıfı - iç üyeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- TaskScheduler class [.NET Framework debug engines]
- debug engines, TaskScheduler class [.NET Framework]
ms.assetid: 87f1c969-0217-4464-8907-7609c1bf61d3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 18cd3ec809df921d6baefbf8018fefc77db238d3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126770"
---
# <a name="taskscheduler-class---internal-members"></a>TaskScheduler sınıfı - iç üyeleri
Bu konuda iç üyeleri açıklanmaktadır <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName> yardımcı sınıf özel bir hata ayıklayıcı uygulama. Bu sınıf hakkında genel bilgi için bkz: <xref:System.Threading.Tasks.TaskScheduler> başvuru konusu.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Derleme:** mscorlib (içinde mscorlib.dll)  
  
 İç bu üye .NET Framework'teki erişemediği için aşağıdaki söz dizimini ortak Ara dile (CIL) sağlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
.class public abstract auto ansi beforefieldinit System.Threading.Tasks.TaskScheduler  
       extends System.Object  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[GetScheduledTasksForDebugger](../../extensibility/debugger/getscheduledtasksfordebugger-method.md)|Tüm zamanlanmış görevlerin dizisini alır.|  
|[GetTaskSchedulersForDebugger](../../extensibility/debugger/gettaskschedulersfordebugger-method.md)|Tüm dizisini alır <xref:System.Threading.Tasks.TaskScheduler> şu an etkin olan nesneleri.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>   
 [.NET Framework için Paralel Uzantı Dahili Bileşenleri](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)