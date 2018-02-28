---
title: MODULE_INFO | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MODULE_INFO
helpviewer_keywords:
- MODULE_INFO structure
ms.assetid: f2e06180-1ab3-4eb5-a428-7994cceb61b6
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: fd49230165282dd656252c4edaabfbaa31d43340
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="moduleinfo"></a>MODULE_INFO
Belirli bir modülün (DLL, EXE veya derleme) açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct tagMODULE_INFO {   
   MODULE_INFO_FIELDS dwValidFields;  
   BSTR               m_bstrName;  
   BSTR               m_bstrUrl;  
   BSTR               m_bstrVersion;  
   BSTR               m_bstrDebugMessage;  
   UINT64             m_addrLoadAddress;  
   UINT64             m_addrPreferredLoadAddress;  
   DWORD              m_dwSize;  
   DWORD              m_dwLoadOrder;  
   FILETIME           m_TimeStamp;  
   BSTR               m_bstrUrlSymbolLocation;  
   MODULE_FLAGS       m_dwModuleFlags;  
} MODULE_INFO;  
```  
  
```csharp  
public struct MODULE_INFO {   
   public uint     dwValidFields;  
   public string   m_bstrName;  
   public string   m_bstrUrl;  
   public string   m_bstrVersion;  
   public string   m_bstrDebugMessage;  
   public ulong    m_addrLoadAddress;  
   public ulong    m_addrPreferredLoadAddress;  
   public uint     m_dwSize;  
   public uint     m_dwLoadOrder;  
   public FILETIME m_TimeStamp;  
   public string   m_bstrUrlSymbolLocation;  
   public uint     m_dwModuleFlags;  
};  
```  
  
## <a name="members"></a>Üyeler  
 dwValidFields  
 Bayraklarını bileşimini [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md) hangi alanların doldurulmuş belirtir numaralandırması.  
  
 m_bstrName  
 Modül adı.  
  
 m_bstrUrl  
 Modül URL'si.  
  
 m_bstrVersion  
 Modül sürümü.  
  
 m_bstrDebugMessage  
 İsteğe bağlı bir ileti modülü hakkında Örneğin, "simgeleri yüklenemiyor."  
  
 m_addrLoadAddress  
 Modül yük adresi.  
  
 m_addrPreferredLoadAddress  
 Modül tercih edilen yük adresi.  
  
 m_dwSize  
 Modül boyutu.  
  
 m_dwLoadOrder  
 Modül yükleme sırası.  
  
 m_TimeStamp  
 Simge dosyanın son değiştirilme saati.  
  
 m_bstrUrlSymbolLocation  
 Simge dosyanın konumunu (örneğin, ".\\") modülü belirtilmiş. Sembolleri için bir modülü bulmak için bir başlangıç konumu olarak kullanılır.  
  
 m_dwModuleFlags  
 Bayraklarını bileşimini [MODULE_FLAGS](../../../extensibility/debugger/reference/module-flags.md) modülü açıklar numaralandırması.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı geçirilir [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md) yöntemi burada bunu doldurulur.  
  
 Bu yapı, listelenen her modül karşılık gelen **modülleri** penceresi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)   
 [MODULE_FLAGS](../../../extensibility/debugger/reference/module-flags.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)