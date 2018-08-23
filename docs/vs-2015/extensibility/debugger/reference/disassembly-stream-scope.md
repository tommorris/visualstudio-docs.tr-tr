---
title: DISASSEMBLY_STREAM_SCOPE | Microsoft Docs
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
- DISASSEMBLY_STREAM_SCOPE
helpviewer_keywords:
- DISASSEMBLY_STREAM_SCOPE enumeration
ms.assetid: 43e2b364-cbbe-4755-a7e6-a03f3054c965
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 57ab3a78da8629a21797c52416e03edc99f5666d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690346"
---
# <a name="disassemblystreamscope"></a>DISASSEMBLY_STREAM_SCOPE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [DISASSEMBLY_STREAM_SCOPE](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/disassembly-stream-scope).  
  
Ayrıştırılmış kod akışın kapsamını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
enum enum_DISASSEMBLY_STREAM_SCOPE {   
   DSS_HUGE     = 0x10000000,  
   DSS_FUNCTION = 0x0001,  
   DSS_MODULE   = (DSS_HUGE) | 0x0002,  
   DSS_ALL      = (DSS_HUGE) | 0x0003  
};  
typedef DWORD DISASSEMBLY_STREAM_SCOPE;  
```  
  
```csharp  
public enum enum_DISASSEMBLY_STREAM_SCOPE {   
   DSS_HUGE     = 0x10000000,  
   DSS_FUNCTION = 0x0001,  
   DSS_MODULE   = (DSS_HUGE) | 0x0002,  
   DSS_ALL      = (DSS_HUGE) | 0x0003  
};  
```  
  
## <a name="members"></a>Üyeler  
 DSS_HUGE  
 Kod bağlamı derlemesini açma işlemlerini uygulama istemci genellikle tek bir çağrıda almak daha daha fazla çıkış karşılaşırsınız belirtir.  
  
 DSS_FUNCTION  
 Kod kapsamında yer alan işlevi çözülürken olduğunu belirtir. Ayrıştırılmış kod akış tarafından döndürülen bir işlevi temsil ettiğini belirtir [GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md) yöntemi.  
  
 DSS_MODULE  
 Tarafından döndürülen `IDebugDisassemblyStream2::GetScope` yöntemi Ayrıştırılmış kod akış bir modülü temsil ettiğini belirtir.  
  
 DSS_ALL  
 Tüm adres için ayrıştırılmış kodu belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bağımsız değişken olarak geçirilen [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md) yöntemi ve tarafından döndürülen [GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md) yöntemi.  
  
 Bu değerler, bit düzeyinde ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)   
 [GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md)

