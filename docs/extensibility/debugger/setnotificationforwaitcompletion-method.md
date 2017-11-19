---
title: "SetNotificationForWaitCompletion yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SetNotificationForWaitCompletion method, Task class [.NET Framework debug engines]
ms.assetid: da149c9a-20f4-4543-a29e-429c8c1d2e19
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 385ae98e90d8f3a466c0983405c367347bb8ca10
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="setnotificationforwaitcompletion-method"></a>SetNotificationForWaitCompletion yöntemi
Ayarlar veya TASK_STATE_WAIT_COMPLETION_NOTIFICATION durumu bit temizler.  
  
 **Namespace:**<xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Derleme:** mscorlib (içinde mscorlib.dll)  
  
## <a name="syntax"></a>Sözdizimi  
  
```vb  
internal void SetNotificationForWaitCompletion(bool enabled)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `enabled`  
  
 `true`bit ayarlamak için; `false` çok unset bit.  
  
## <a name="exceptions"></a>Özel Durumlar  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklayıcıyı zaman uyumsuz yöntem gövdesi dışında adım yardımcı olmak için bu bit ayarlar. Varsa `enabled` olan `true`, bu yöntem, henüz tamamlanmamış bir görevde çağrılmalıdır. Varsa `enabled` olan `false`, bu yöntem üzerinde tamamlanan görevler çağrılabilir. Ya da bir olay, onu yalnızca promise stili görevler için kullanılmalıdır.  
  
## <a name="requirements"></a>Gereksinimler  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Task sınıfı](../../extensibility/debugger/task-class-internal-members.md)