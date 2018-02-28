---
title: PROCESS_INFO_FLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PROCESS_INFO_FLAGS
helpviewer_keywords:
- PROCESS_INFO_FLAGS enumeration
ms.assetid: 696951ce-701a-40c2-ac8c-b897f3aae6e2
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9ff1df7e73c8f09934504552f33d7f9ce4c537e4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="processinfoflags"></a>PROCESS_INFO_FLAGS
Açıklar veya bir işlem özelliklerini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_PROCESS_INFO_FLAGS {   
   PIFLAG_SYSTEM_PROCESS    = 0x00000001,  
   PIFLAG_DEBUGGER_ATTACHED = 0x00000002,  
   PIFLAG_PROCESS_STOPPED   = 0x00000004,  
   PIFLAG_PROCESS_RUNNING   = 0x00000008,  
};  
typedef DWORD PROCESS_INFO_FLAGS;  
```  
  
```csharp  
enum enum_PROCESS_INFO_FLAGS {   
   PIFLAG_SYSTEM_PROCESS    = 0x00000001,  
   PIFLAG_DEBUGGER_ATTACHED = 0x00000002,  
   PIFLAG_PROCESS_STOPPED   = 0x00000004,  
   PIFLAG_PROCESS_RUNNING   = 0x00000008,  
};  
```  
  
## <a name="members"></a>Üyeler  
 PIFLAG_SYSTEM_PROCESS  
 İşlem bir sistem işlemi olduğunu gösterir.  
  
 PIFLAG_DEBUGGER_ATTACHED  
 İşlemi bir hata ayıklayıcı tarafından ayıklanacak gösterir. Bu olabilir bir [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] hata ayıklayıcı veya bazı diğer hata ayıklayıcı, örneğin, WinDbg olabilir.  
  
 PIFLAG_PROCESS_STOPPED  
 İşlem durduruldu gösterir. Geçerli eksikse `PIFLAG_DEBUGGER_ATTACHED` da belirtilmiş. Kullanılabilir [!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)] ve daha sonra.  
  
 PIFLAG_PROCESS_RUNNING  
 İşlemin çalışmadığını gösterir. Geçerli eksikse `PIFLAG_DEBUGGER_ATTACHED` da belirtilmiş. Kullanılabilir [!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)] ve daha sonra.  
  
## <a name="remarks"></a>Açıklamalar  
 İçin kullanılan `Flags` üyesi [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) yapısı.  
  
 Bu bayrakların bit ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)