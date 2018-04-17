---
title: BP_COND_STYLE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BP_COND_STYLE
helpviewer_keywords:
- BP_COND_STYLE enumeration
ms.assetid: a93b1412-f447-48a1-af9d-38f3dbb3092f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 64c3ac876f0d7be8582ca8162fd93c83cb6d343e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="bpcondstyle"></a>BP_COND_STYLE
Kesme noktası koşul stili bekleyen belirtir ve bağlı kesme noktaları.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_BP_COND_STYLE {   
   BP_COND_NONE         = 0x0000,  
   BP_COND_WHEN_TRUE    = 0x0001,  
   BP_COND_WHEN_CHANGED = 0x0002  
};  
typedef DWORD BP_COND_STYLE;  
```  
  
```csharp  
public enum enum_BP_COND_STYLE {   
   BP_COND_NONE         = 0x0000,  
   BP_COND_WHEN_TRUE    = 0x0001,  
   BP_COND_WHEN_CHANGED = 0x0002  
};  
```  
  
## <a name="members"></a>Üyeler  
 BP_COND_NONE  
 Kesme noktası'nın konumunu ulaşıldığında kesme ateşlenir. Kesme noktası koşul belirtildi.  
  
 BP_COND_WHEN_TRUE  
 Kesme noktası değerlendiren zaman koşullu ifade kesme noktası ile ilişkili yalnızca ateşlenir `true`.  
  
 BP_COND_WHEN_CHANGED  
 Yalnızca koşullu ifade değerini kesme noktası ile ilişkili kırılma, önceki değerlendirme sürümünden değişti ateşlenir.  
  
## <a name="remarks"></a>Açıklamalar  
 İçin kullanılan `styleCondition` üyesi [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) yapısı.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)