---
title: PROCESS_INFO_FIELDS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- PROCESS_INFO_FIELDS
helpviewer_keywords:
- PROCESS_INFO_FIELDS enumeration
ms.assetid: 0d9cc345-3d3a-44d8-ae15-a67acb97a828
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3376db379e4e911bcaa8e865a16c63d1251229f6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="processinfofields"></a>PROCESS_INFO_FIELDS
Ne tür bilgileri almak için bir işlem için belirtilen.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_PROCESS_INFO_FIELDS {   
   PIF_FILE_NAME             = 0x00000001,  
   PIF_BASE_NAME             = 0x00000002,  
   PIF_TITLE                 = 0x00000004,  
   PIF_PROCESS_ID            = 0x00000008,  
   PIF_SESSION_ID            = 0x00000010,  
   PIF_ATTACHED_SESSION_NAME = 0x00000020,  
   PIF_CREATION_TIME         = 0x00000040,  
   PIF_FLAGS                 = 0x00000080,  
   PIF_ALL                   = 0x000000ff  
};  
typedef DWORD PROCESS_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_PROCESS_INFO_FIELDS {   
   PIF_FILE_NAME             = 0x00000001,  
   PIF_BASE_NAME             = 0x00000002,  
   PIF_TITLE                 = 0x00000004,  
   PIF_PROCESS_ID            = 0x00000008,  
   PIF_SESSION_ID            = 0x00000010,  
   PIF_ATTACHED_SESSION_NAME = 0x00000020,  
   PIF_CREATION_TIME         = 0x00000040,  
   PIF_FLAGS                 = 0x00000080,  
   PIF_ALL                   = 0x000000ff  
};  
```  
  
## <a name="members"></a>Üyeler  
 PIF_FILE_NAME  
 Başlatma/kullanım `bstrFileName` alanını [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) yapısı.  
  
 PIF_BASE_NAME  
 Başlatma/kullanım `bstrBaseName` alanını `PROCESS_INFO` yapısı.  
  
 PIF_TITLE  
 Başlatma/kullanım `bstrTitle` alanını `PROCESS_INFO` yapısı.  
  
 PIF_PROCESS_ID  
 Başlatma/kullanım `ProcessId` alanını `PROCESS_INFO` yapısı.  
  
 PIF_SESSION_ID  
 Başlatma/kullanım `dwSessionId` alanını `PROCESS_INFO` yapısı.  
  
 PIF_ATTACHED_SESSION_NAME  
 Başlatma/kullanım `bstrAttachedSessionName` alanını `PROCESS_INFO` yapısı.  
  
 PIF_CREATION_TIME  
 Başlatma/kullanım `CreationTime` alanını `PROCESS_INFO` yapısı.  
  
 PIF_FLAGS  
 Başlatma/kullanım `Flags` alanını `PROCESS_INFO` yapısı.  
  
 PIF_ALL  
 Tüm alanları doldurur.  
  
## <a name="remarks"></a>Açıklamalar  
 Geçirilen [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md) hangi alanlarının belirtmek için yöntemi [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) yapısı başlatılması üzeresiniz.  
  
 Ayrıca kullanılan `Fields` alanını `PROCESS_INFO` hangi alanların kullanılan ve geçerli olduğunu belirtmek için yapısı.  
  
 Bu bayrakların bit ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)