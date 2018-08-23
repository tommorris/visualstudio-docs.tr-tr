---
title: SetNotificationForWaitCompletion metodu | Microsoft Docs
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
- SetNotificationForWaitCompletion method, Task class [.NET Framework debug engines]
ms.assetid: da149c9a-20f4-4543-a29e-429c8c1d2e19
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9b1443bbbd49216330d1df9978052bf4d10f7157
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629753"
---
# <a name="setnotificationforwaitcompletion-method"></a>SetNotificationForWaitCompletion Metodu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [SetNotificationForWaitCompletion metodu](https://docs.microsoft.com/visualstudio/extensibility/debugger/setnotificationforwaitcompletion-method).  
  
Ayarlar veya TASK_STATE_WAIT_COMPLETION_NOTIFICATION durumu bit temizler.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Bütünleştirilmiş kod:** mscorlib (mscorlib.dll içinde)  
  
## <a name="syntax"></a>Sözdizimi  
  
```vb  
internal void SetNotificationForWaitCompletion(bool enabled)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `enabled`  
  
 `true` bit ayarlamak için; `false` çok unset bit.  
  
## <a name="exceptions"></a>Özel Durumlar  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklayıcı adım bir zaman uyumsuz yöntem gövdesinin dışında yardımcı olmak için bu bit ayarlar. Varsa `enabled` olduğu `true`, yalnızca henüz tamamlanmamış bir görev üzerinde bu yöntem çağrılmalıdır. Varsa `enabled` olduğu `false`, tamamlanan görevler üzerinde bu yöntem çağrılabilir. Ya da bir olay, yalnızca promise stili görevler için kullanılmalıdır.  
  
## <a name="requirements"></a>Gereksinimler  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev sınıfı](../../extensibility/debugger/task-class-internal-members.md)

