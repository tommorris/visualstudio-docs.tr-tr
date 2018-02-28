---
title: EXCEPTION_INFO | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- EXCEPTION_INFO
helpviewer_keywords:
- EXCEPTION_INFO structure
ms.assetid: d046957a-b97d-420b-b46b-c67cbaef709e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 6ae273934cc3224a189c94f371fdbe1e3bcc1c68
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="exceptioninfo"></a>EXCEPTION_INFO
Bir özel durum ya da çalışma zamanı hatası ayıklanacak program tarafından oluşturulan açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct tagEXCEPTION_INFO {   
   IDebugProgram2* pProgram;  
   BSTR            bstrProgramName;  
   BSTR            bstrExceptionName;  
   DWORD           dwCode;  
   EXCEPTION_STATE dwState;  
   GUID            guidType;  
} EXCEPTION_INFO;  
```  
  
```csharp  
public struct EXCEPTION_INFO {   
   public IDebugProgram2 pProgram;  
   public string         bstrProgramName;  
   public string         bstrExceptionName;  
   public uint           dwCode;  
   public uint           dwState;  
   public Guid           guidType;  
};  
```  
  
## <a name="members"></a>Üyeler  
 pProgram  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) özel durumun meydana geldiği programı temsil eden nesne.  
  
 bstrProgramName  
 Özel durumun meydana geldiği programın adı.  
  
 bstrExceptionName  
 Özel durum adı.  
  
 dwCode  
 Özel durum ya da çalışma zamanı hata kimliği kodu.  
  
 dwState  
 Arasında bir değer [EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md) özel durumunu tanımlar numaralandırması.  
  
 guidType  
 GUID dil tanımlayıcısı, her iki `guidLang` veya `guidEng`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı için bir parametre olarak geçirilen [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md) ve [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md) yöntemleri. Bu yapı de geçirilir [GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md) doldurulacak yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)   
 [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)   
 [GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md)