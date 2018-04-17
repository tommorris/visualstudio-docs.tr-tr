---
title: PARSEFLAGS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- PARSEFLAGS
helpviewer_keywords:
- PARSEFLAGS enumeration
ms.assetid: 47943f0a-54cb-4493-a62e-5dba97bd4c35
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 70766aef19c199a191f141947f1b5a458450c322
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="parseflags"></a>PARSEFLAGS
Bir ifade ayrıştırmayı belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_PARSEFLAGS {   
   PARSE_EXPRESSION            = 0x0001,  
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,  
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000  
};  
typedef DWORD PARSEFLAGS;  
```  
  
```csharp  
public enum enum_PARSEFLAGS {   
   PARSE_EXPRESSION            = 0x0001,  
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,  
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000  
};  
```  
  
## <a name="members"></a>Üyeler  
 PARSE_EXPRESSION  
 İfade bir ifade değil gösterir.  
  
 PARSE_FUNCTION_AS_ADDRESS  
 İfade bir adresi olarak ayrıştırılması (ve daha sonra değerlendirilmesi için) olduğunu gösterir.  
  
 PARSE_DESIGN_TIME_EXPR_EVAL  
 İfade tasarım sırasında Ayrıştırılmakta olan gösterir (diğer bir deyişle, bir tasarımcı açık olduğunda).  
  
## <a name="remarks"></a>Açıklamalar  
 Bir parametre olarak geçirilen [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) ve [ayrıştırma](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) yöntemleri.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)   
 [Ayrıştırma](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)