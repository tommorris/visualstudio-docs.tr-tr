---
title: TASK_STATE_CANCELED alanı | Microsoft Docs
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
- TASK_STATE_CANCELED field, Task class [.NET Framework debug engines]
ms.assetid: f4f5a96a-8230-493d-9696-8d2716bda261
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 869553b18f16135fe81d1a33e64eba1d33f0990b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687143"
---
# <a name="taskstatecanceled-field"></a>TASK_STATE_CANCELED Alanı
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [TASK_STATE_CANCELED alanı](https://docs.microsoft.com/visualstudio/extensibility/debugger/task-state-canceled-field).  
  
Görev çalışma durumuna ulaştı veya kendi iptal onaylanır ve özel durum tamamlandı önce iptal edildi.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Bütünleştirilmiş kod:** mscorlib (mscorlib.dll içinde)  
  
 .NET Framework'den bu iç üye erişemediği için aşağıdaki söz dizimini ortak Ara dil (CIL) sağlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
.field static assembly literal int32 TASK_STATE_CANCELED = int32(0x00800000)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa [m_stateFlags](../../extensibility/debugger/m-stateflags-field.md) alan içerir, bu değer <xref:System.Threading.Tasks.Task.Status%2A> özelliği döndürür <xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev sınıfı](../../extensibility/debugger/task-class-internal-members.md)

