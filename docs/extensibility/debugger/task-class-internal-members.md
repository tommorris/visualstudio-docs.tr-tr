---
title: "Task sınıfı - iç üyeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debug engines, Task class [.NET Framework]
- Task class [.NET Framework debug engines]
ms.assetid: 28e47c3b-9323-424a-80ac-6cc3bf19e09b
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: b92a622b6b898c917710ac748b9205079d71ea5e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="task-class---internal-members"></a>Task sınıfı - iç üyeleri
Bu konuda iç üyeleri açıklanmaktadır <xref:System.Threading.Tasks.Task?displayProperty=fullName> yardımcı sınıf özel bir hata ayıklayıcı uygulama. Bu sınıf hakkında genel bilgi için bkz: <xref:System.Threading.Tasks.Task> başvuru konusu.  
  
 **Namespace:**<xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Derleme:** mscorlib (içinde mscorlib.dll)  
  
 İç bu üye .NET Framework'teki erişemediği için aşağıdaki söz dizimini ortak Ara dile (CIL) sağlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
.class public auto ansi System.Threading.Tasks.Task  
       extends System.Object  
       implements System.Threading.IThreadPoolWorkItem,  
                  System.IAsyncResult,  
                  System.IDisposable,  
                  System.Threading.ICancelableOperation  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SetNotificationForWaitCompletion Metodu](../../extensibility/debugger/setnotificationforwaitcompletion-method.md)|Ayarlar veya TASK_STATE_WAIT_COMPLETION_NOTIFICATION durumu bit temizler.|  
|[NotifyDebuggerOfWaitCompletion Metodu](../../extensibility/debugger/notifydebuggerofwaitcompletion-method.md)|Hata ayıklayıcı tarafından bir kesme noktası hedefi olarak kullanılan yer tutucu yöntemi.|  
  
### <a name="fields"></a>Alanlar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[m_action](../../extensibility/debugger/m-action-field.md)|İçinde yürütmek için kodu temsil eden temsilci <xref:System.Threading.Tasks.Task> nesnesi.|  
|[m_contingentProperties](../../extensibility/debugger/m-contingentproperties-field.md)|Ek özelliklerini depolayan <xref:System.Threading.Tasks.Task> nesnesi.|  
|[m_parent](../../extensibility/debugger/m-parent-field.md)|Yedekleme alanı için <xref:System.Threading.Tasks.Task?displayProperty=fullName> üst özelliği.|  
|[m_stateFlags](../../extensibility/debugger/m-stateflags-field.md)|Geçerli durumuyla ilgili bilgileri depolar <xref:System.Threading.Tasks.Task> nesnesi.|  
|[m_stateObject](../../extensibility/debugger/m-stateobject-field.md)|Eylem tarafından kullanılan verileri temsil eden nesne.|  
|[m_taskId](../../extensibility/debugger/m-taskid-field.md)|Yedekleme alanı için <xref:System.Threading.Tasks.Task.Id%2A?displayProperty=fullName> özelliği.|  
|[s_taskIdCounter](../../extensibility/debugger/s-taskidcounter-field.md)|Sonraki kullanılabilir tanımlayıcısını bir <xref:System.Threading.Tasks.Task> nesnesi.|  
|[TASK_STATE_CANCELED](../../extensibility/debugger/task-state-canceled-field.md)|Çalışır duruma ulaştı önce görev iptal edildi veya görev kendi iptal onaylanır ve özel durum olmadan tamamlandı gösterir.|  
|[TASK_STATE_EXECUTED](../../extensibility/debugger/task-state-executed-field.md)|Görevin çalıştığı gösterir.|  
|[TASK_STATE_FAULTED](../../extensibility/debugger/task-state-faulted-field.md)|Görev işlenmeyen bir özel durum nedeniyle tamamlandı gösterir.|  
|[TASK_STATE_RAN_TO_COMPLETION](../../extensibility/debugger/task-state-ran-to-completion-field.md)|Görev Yürütme başarıyla tamamlanıp tamamlanmadığını gösterir.|  
|[TASK_STATE_WAITING_ON_CHILDREN](../../extensibility/debugger/task-state-waiting-on-children-field.md)|Görev, temsilci yürütülmesi tamamlandı ve dolaylı olarak bağlı alt görevin bitmesini bekliyor gösterir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Girişinin işaretlemek için aşağıdaki iç yöntemleri bir hata ayıklayıcı altyapısı yararlıdır <xref:System.Threading.Tasks.Task> kod yürütme:  
  
-   `Execute`  
  
-   `ExecuteEntry`  
  
-   `ExecuteWithThreadLocal`  
  
-   `Finish`  
  
-   `InnerInvoke`  
  
-   `InternalWait`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Threading.Tasks.Task?displayProperty=fullName>   
 [.NET Framework için Paralel Uzantı Dahili Bileşenleri](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)