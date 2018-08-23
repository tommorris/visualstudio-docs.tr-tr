---
title: GetScheduledTasksForDebugger metodu | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- GetScheduledTasksForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 7c9b4cde-6e4a-4cef-929f-7d02b1da5762
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bf2649dbb3e2a4b5cd614f078c461217044ee08b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689447"
---
# <a name="getscheduledtasksfordebugger-method"></a>GetScheduledTasksForDebugger Metodu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [GetScheduledTasksForDebugger metodu](https://docs.microsoft.com/visualstudio/extensibility/debugger/getscheduledtasksfordebugger-method).  
  
Tüm zamanlanmış görevlerin dizisini alır.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Bütünleştirilmiş kod:** mscorlib (mscorlib.dll içinde)  
  
 .NET Framework'den bu iç üye erişemediği için aşağıdaki söz dizimini ortak Ara dil (CIL) sağlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
.method assembly hidebysig instance class System.Threading.Tasks.Task[] GetScheduledTasksForDebugger() cil managed  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Tüm zamanlanmış görevlerin dizisi. Her görev, yürütülmekte olan veya yürütülmesi tamamlandı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem iş parçacığı güvenli değildir ve diğer örnekleri aynı anda kullanılmamalıdır <xref:System.Threading.Tasks.TaskScheduler> yalnızca hata ayıklayıcı, diğer tüm iş parçacıkları askıya olduğunda, hata ayıklayıcı'dan çağrılmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [TaskScheduler sınıfı](../../extensibility/debugger/taskscheduler-class-internal-members.md)

