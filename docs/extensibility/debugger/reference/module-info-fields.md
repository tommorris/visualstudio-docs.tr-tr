---
title: MODULE_INFO_FIELDS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- MODULE_INFO_FIELDS
helpviewer_keywords:
- MODULE_INFO_FIELDS enumeration
ms.assetid: 8bed85f4-235f-4192-b58f-5fad7a4d7a78
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fcc6bd76a4a9aecade72347613ed4f36968c65eb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31125935"
---
# <a name="moduleinfofields"></a>MODULE_INFO_FIELDS
Hata ayıklama modül bilgilerini bayrakları belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_MODULE_INFO_FIELDS {   
   MIF_NONE              = 0x0000,  
   MIF_NAME              = 0x0001,  
   MIF_URL               = 0x0002,  
   MIF_VERSION           = 0x0004,  
   MIF_DEBUGMESSAGE      = 0x0008,  
   MIF_LOADADDRESS       = 0x0010,  
   MIF_PREFFEREDADDRESS  = 0x0020,  
   MIF_SIZE              = 0x0040,  
   MIF_LOADORDER         = 0x0080,  
   MIF_TIMESTAMP         = 0x0100,  
   MIF_URLSYMBOLLOCATION = 0x0200,  
   MIF_FLAGS             = 0x0400,  
   MIF_ALLFIELDS         = 0x07ff  
};  
typedef DWORD MODULE_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_MODULE_INFO_FIELDS {   
   MIF_NONE              = 0x0000,  
   MIF_NAME              = 0x0001,  
   MIF_URL               = 0x0002,  
   MIF_VERSION           = 0x0004,  
   MIF_DEBUGMESSAGE      = 0x0008,  
   MIF_LOADADDRESS       = 0x0010,  
   MIF_PREFFEREDADDRESS  = 0x0020,  
   MIF_SIZE              = 0x0040,  
   MIF_LOADORDER         = 0x0080,  
   MIF_TIMESTAMP         = 0x0100,  
   MIF_URLSYMBOLLOCATION = 0x0200,  
   MIF_FLAGS             = 0x0400,  
   MIF_ALLFIELDS         = 0x07ff  
};  
```  
  
## <a name="members"></a>Üyeler  
 MIF_NONE  
 Yapısında alanlarının hiçbiri başlatma/kullanın.  
  
 MIF_NAME  
 Başlatma/kullanım `m_bstrName` alanındaki [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) yapısı.  
  
 MIF_URL  
 Başlatma/kullanım `m_bstrUrl` alanındaki `MODULE_INFO` yapısı.  
  
 MIF_VERSION  
 Başlatma/kullanım `m_bstrVersion` alanındaki `MODULE_INFO` yapısı.  
  
 MIF_DEBUGMESSAGE  
 Başlatma/kullanım `m_bstrDebugMessage` alanındaki `MODULE_INFO` yapısı.  
  
 MIF_LOADADDRESS  
 Başlatma/kullanım `m_addrLoadAddress` alanındaki `MODULE_INFO` yapısı.  
  
 MIF_PREFFEREDADDRESS  
 Başlatma/kullanım `m_addrPreferredLoadAddress` alanındaki `MODULE_INFO` yapısı.  
  
 MIF_SIZE  
 Başlatma/kullanım `m_dwSize` alanındaki `MODULE_INFO` yapısı.  
  
 MIF_LOADORDER  
 Başlatma/kullanım `m_dwLoadOrder` alanındaki `MODULE_INFO` yapısı.  
  
 MIF_TIMESTAMP  
 Başlatma/kullanım `m_TimeStamp` alanındaki `MODULE_INFO` yapısı.  
  
 MIF_URLSYMBOLLOCATION  
 Başlatma/kullanım `m_bstrUrlSymbolLocation` alanındaki `MODULE_INFO` yapısı.  
  
 MIF_FLAGS  
 Başlatma/kullanım `m_dwModuleFlags` alanındaki `MODULE_INFO` yapısı.  
  
 MIF_ALLFIELDS  
 Tüm alanların başlatma/kullanım `MODULE_INFO` yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu değerler için bağımsız değişken olarak geçirilen [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md) hangi alanlarının belirtmek için yöntemi [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) yapısı başlatılması üzeresiniz.  
  
 Bu değerleri de içinde kullanılan `MODULE_INFO` hangi alanların kullanılan ve geçerli olduğunu belirtmek için yapısı.  
  
 Bu bayrakların bit ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)