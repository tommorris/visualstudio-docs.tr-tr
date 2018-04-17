---
title: EVALFLAGS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- EVALFLAGS
helpviewer_keywords:
- EVALFLAGS enumeration
ms.assetid: 7b2cb14a-511a-4fef-9e4f-308139719fba
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7c718414749bb6c748f25fb90837644fe984a274
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="evalflags"></a>EVALFLAGS
İfade değerlendirme denetim bayrakları belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_EVALFLAGS {  
   EVAL_RETURNVALUE = 0x0002,  
   EVAL_NOSIDEEFFECTS = 0x0004,  
   EVAL_ALLOWBPS = 0x0008,  
   EVAL_ALLOWERRORREPORT = 0x0010,  
   EVAL_FUNCTION_AS_ADDRESS = 0x0040,  
   EVAL_NOFUNCEVAL = 0x0080,  
   EVAL_NOEVENTS = 0x1000  
};  
typedef DWORD EVALFLAGS;  
```  
  
```csharp  
public enum enum_EVALFLAGS {  
   EVAL_RETURNVALUE = 0x0002,  
   EVAL_NOSIDEEFFECTS = 0x0004,  
   EVAL_ALLOWBPS = 0x0008,  
   EVAL_ALLOWERRORREPORT = 0x0010,  
   EVAL_FUNCTION_AS_ADDRESS = 0x0040,  
   EVAL_NOFUNCEVAL = 0x0080,  
   EVAL_NOEVENTS = 0x1000  
}  
```  
  
## <a name="members"></a>Üyeler  
 EVAL_RETURNVALUE  
 Dönüş değeri varsa değerlendirilmesi belirtir.  
  
 EVAL_NOSIDEEFFECTS  
 Yan etkileri değil verileceğini belirtir.  
  
 EVAL_ALLOWBPS  
 Durdurma kesme noktaları üzerinde belirtir.  
  
 EVAL_ALLOWERRORREPORT  
 Hata izin verilmesi için konağa raporlama belirtir. Internet Explorer'da komut ifade değerlendirmesi için kullanılır.  
  
 EVAL_FUNCTION_AS_ADDRESS  
 İşlev çağırma yerine adresleri olarak değerlendirilecek işlevler zorlar.  
  
 EVAL_NOFUNCEVAL  
 İşlev değerlendirilen gelen engeller. Örneğin, göz önünde bulundurun `int` ifadesinde belirteci `myExpression(int) + 10`. Bu işlev doğru adresi olarak ancak olmayan bir değer olarak değerlendirilebilir.  
  
 EVAL_NOEVENTS  
 İfade değerlendirme sırasında meydana gelen olayları oturum hata ayıklama Yöneticisi'ni (SDM) ya da IDE gönderilmemelidir belirtmek için bayraklayın.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu bayrakların bağımsız değişken olarak geçirilen [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) ve [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) yöntemleri.  
  
 Bu bayrakların bit düzeyinde OR ile birleştirilebilir.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)