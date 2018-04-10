---
title: NotifyDebuggerOfWaitCompletion yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- NotifyDebuggerOfWaitCompletion method, Task class [.NET Framework debug engines]
ms.assetid: 841c5908-4f3f-400b-a7b0-96a95f362817
caps.latest.revision: 5
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: d28b6d4eb18535cbfef39790b544288ad39659c3
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="notifydebuggerofwaitcompletion-method"></a>NotifyDebuggerOfWaitCompletion Method
Hata ayıklayıcı tarafından bir kesme noktası hedefi olarak kullanılan yer tutucu yöntemi. Bu yöntem, satır içi veya en iyi duruma getirilmiş olmamalıdır.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Derleme:** mscorlib (içinde mscorlib.dll)  
  
## <a name="syntax"></a>Sözdizimi  
  
```vb  
private void NotifyDebuggerOfWaitCompletion()  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kendi hata ayıklayıcı bildirim biti ayarlanmışsa görevle ilgili tüm birleştirme işlemleri bu yöntemi çağırmanız gerekir.  
  
## <a name="requirements"></a>Gereksinimler  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Task sınıfı](../../extensibility/debugger/task-class-internal-members.md)