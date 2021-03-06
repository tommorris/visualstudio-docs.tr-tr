---
title: PROCESS_INFO_FIELDS | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- PROCESS_INFO_FIELDS
helpviewer_keywords:
- PROCESS_INFO_FIELDS enumeration
ms.assetid: 0d9cc345-3d3a-44d8-ae15-a67acb97a828
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8b272fba2e05c25e60b2db1f11be16b97d261101
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689850"
---
# <a name="processinfofields"></a>PROCESS_INFO_FIELDS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [PROCESS_INFO_FIELDS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/process-info-fields).  
  
Hangi tür bilgiler almak için bir işlem için belirtilen.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 Başlat/kullanım `bstrFileName` alanını [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) yapısı.  
  
 PIF_BASE_NAME  
 Başlat/kullanım `bstrBaseName` alanını `PROCESS_INFO` yapısı.  
  
 PIF_TITLE  
 Başlat/kullanım `bstrTitle` alanını `PROCESS_INFO` yapısı.  
  
 PIF_PROCESS_ID  
 Başlat/kullanım `ProcessId` alanını `PROCESS_INFO` yapısı.  
  
 PIF_SESSION_ID  
 Başlat/kullanım `dwSessionId` alanını `PROCESS_INFO` yapısı.  
  
 PIF_ATTACHED_SESSION_NAME  
 Başlat/kullanım `bstrAttachedSessionName` alanını `PROCESS_INFO` yapısı.  
  
 PIF_CREATION_TIME  
 Başlat/kullanım `CreationTime` alanını `PROCESS_INFO` yapısı.  
  
 PIF_FLAGS  
 Başlat/kullanım `Flags` alanını `PROCESS_INFO` yapısı.  
  
 PIF_ALL  
 Tüm alanları doldurur.  
  
## <a name="remarks"></a>Açıklamalar  
 Geçirilen [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md) hangi alanları göstermek için yöntemi [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) yapısı olan başlatılacak.  
  
 Ayrıca kullanılan `Fields` alanını `PROCESS_INFO` yapısı hangi alanların kullanılan ve geçerli olduğunu belirtmek için.  
  
 Bu bayrak bit düzeyinde ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)

