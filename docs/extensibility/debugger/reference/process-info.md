---
title: PROCESS_INFO | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- PROCESS_INFO
helpviewer_keywords:
- PROCESS_INFO structure
ms.assetid: 260c33cc-a05e-4645-84b6-536d0b3b0537
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d35b94b6153b65672453ed8b4e7d2c0d9c2bd5eb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134401"
---
# <a name="processinfo"></a>PROCESS_INFO
Bir işlem hakkında bilgi içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct tagPROCESS_INFO {   
   PROCESS_INFO_FIELDS Fields;  
   BSTR                bstrFileName;  
   BSTR                bstrBaseName;  
   BSTR                bstrTitle;  
   AD_PROCESS_ID       ProcessId;  
   DWORD               dwSessionId;  
   BSTR                bstrAttachedSessionName;  
   FILETIME            CreationTime;  
   PROCESS_INFO_FLAGS  Flags;  
} PROCESS_INFO;  
```  
  
```csharp  
public struct PROCESS_INFO {   
   public uint          Fields;  
   public string        bstrFileName;  
   public string        bstrBaseName;  
   public string        bstrTitle;  
   public AD_PROCESS_ID ProcessId;  
   public uint          dwSessionId;  
   public string        bstrAttachedSessionName;  
   public FILETIME      CreationTime;  
   public uint          Flags;  
};  
```  
  
## <a name="members"></a>Üyeler  
 Alanlar  
 Bayraklarını bileşimini [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md) hangi alanların doldurulmuş belirtin numaralandırması.  
  
 bstrFileName  
 İşlemi tam yol adı. Arama eşdeğer [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md) yöntemi parametresi ile `GN_FILENAME`.  
  
 bstrBaseName  
 Dosya adı ve uzantısı işleminin. Arama eşdeğer `IDebugProcess2::Getname` yöntemi parametresi ile `GN_BASENAME`.  
  
 bstrTitle  
 Varsa işlemi, başlığı. Arama eşdeğer `IDebugProcess2::Getname` yöntemi parametresi ile `GN_TITLE`.  
  
 İşlem kimliği  
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) işlemi tanımlayan yapısı. Arama eşdeğer [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md) yöntemi.  
  
 dwSessionId  
 Bu işlemin çalıştığı hata ayıklama oturumu tanımlayıcısı.  
  
 bstrAttachedSessionName  
 Ekli oturum adı. Arama eşdeğer [GetAttachedSessionName](../../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md) yöntemi.  
  
 CreationTime  
 İşlem oluşturulduğu zaman.  
  
 Bayraklar  
 Bayraklarını bileşimini [PROCESS_INFO_FLAGS](../../../extensibility/debugger/reference/process-info-flags.md) numaralandırma işlemi özelliklerini belirtin.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı geçirilir [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md) yöntemi burada bunu doldurulur.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md)   
 [PROCESS_INFO_FLAGS](../../../extensibility/debugger/reference/process-info-flags.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md)   
 [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md)   
 [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)   
 [GetAttachedSessionName](../../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md)