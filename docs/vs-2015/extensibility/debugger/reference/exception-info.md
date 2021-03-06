---
title: EXCEPTION_INFO | Microsoft Docs
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
- EXCEPTION_INFO
helpviewer_keywords:
- EXCEPTION_INFO structure
ms.assetid: d046957a-b97d-420b-b46b-c67cbaef709e
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 152ddae9ad5c3c6b6119c146d428024bc2e26a95
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694755"
---
# <a name="exceptioninfo"></a>EXCEPTION_INFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [EXCEPTION_INFO](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/exception-info).  
  
Bir özel durum veya çalışma zamanı hata ayıklanacak program tarafından oluşturulan açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) özel durumun gerçekleştiği program temsil eden nesne.  
  
 bstrProgramName  
 Özel durum oluştuğu programın adı.  
  
 bstrExceptionName  
 Özel durumun adı.  
  
 dwCode  
 Özel durum veya çalışma zamanı hatası kimlik kodu.  
  
 dwState  
 Bir değer [EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md) özel durumu tanımlayan sabit listesi.  
  
 guidType  
 GUID dil tanımlayıcısı, ya da `guidLang` veya `guidEng`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı için bir parametre olarak geçirilen [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md) ve [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md) yöntemleri. Bu yapı ayrıca geçirilir [GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md) doldurulması için yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimler](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)   
 [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)   
 [GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md)

