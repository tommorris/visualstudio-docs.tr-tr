---
title: EVALFLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: EVALFLAGS
helpviewer_keywords: EVALFLAGS enumeration
ms.assetid: 7b2cb14a-511a-4fef-9e4f-308139719fba
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 45bef946605818f11d0199600849fd49b5463ab8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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