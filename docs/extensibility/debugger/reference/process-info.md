---
title: PROCESS_INFO | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PROCESS_INFO
helpviewer_keywords: PROCESS_INFO structure
ms.assetid: 260c33cc-a05e-4645-84b6-536d0b3b0537
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5628e3cca48799b602917fa1504479b46ee02dd1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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