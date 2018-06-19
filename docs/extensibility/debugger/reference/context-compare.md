---
title: CONTEXT_COMPARE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- CONTEXT_COMPARE
helpviewer_keywords:
- CONTEXT_COMPARE enumeration
ms.assetid: 701ed61c-a320-4c20-a335-0b840024abc0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0563f037f77c18cc5e686c1ea6acf429c91ad06d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31108589"
---
# <a name="contextcompare"></a>CONTEXT_COMPARE
İki bellek bağlamları karşılaştırma ölçütlerini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_CONTEXT_COMPARE {   
   CONTEXT_EQUAL                 = 0x0001,  
   CONTEXT_LESS_THAN             = 0x0002,  
   CONTEXT_GREATER_THAN          = 0x0003,  
   CONTEXT_LESS_THAN_OR_EQUAL    = 0x0004,  
   CONTEXT_GREATER_THAN_OR_EQUAL = 0x0005,  
   CONTEXT_SAME_SCOPE            = 0x0006,  
   CONTEXT_SAME_FUNCTION         = 0x0007,  
   CONTEXT_SAME_MODULE           = 0x0008,  
   CONTEXT_SAME_PROCESS          = 0x0009  
};  
typedef DWORD CONTEXT_COMPARE;  
```  
  
```csharp  
public enum enum_CONTEXT_COMPARE {   
   CONTEXT_EQUAL                 = 0x0001,  
   CONTEXT_LESS_THAN             = 0x0002,  
   CONTEXT_GREATER_THAN          = 0x0003,  
   CONTEXT_LESS_THAN_OR_EQUAL    = 0x0004,  
   CONTEXT_GREATER_THAN_OR_EQUAL = 0x0005,  
   CONTEXT_SAME_SCOPE            = 0x0006,  
   CONTEXT_SAME_FUNCTION         = 0x0007,  
   CONTEXT_SAME_MODULE           = 0x0008,  
   CONTEXT_SAME_PROCESS          = 0x0009  
};  
```  
  
## <a name="members"></a>Üyeler  
 CONTEXT_EQUAL  
 Hedef bellek bağlamına eşittir listedeki ilk bellek bağlam bulun.  
  
 CONTEXT_LESS_THAN  
 Hedef bellek bağlamı'dan küçük listedeki ilk bellek bağlam bulun.  
  
 CONTEXT_GREATER_THAN  
 Hedef bellek bağlamı büyük listedeki ilk bellek bağlam bulun.  
  
 CONTEXT_LESS_THAN_OR_EQUAL  
 Küçük veya eşittir hedef bellek bağlamı listedeki ilk bellek bağlam bulun.  
  
 CONTEXT_GREATER_THAN_OR_EQUAL  
 Büyük veya eşit hedef bellek bağlamı için listedeki ilk bellek bağlam bulun.  
  
 CONTEXT_SAME_SCOPE  
 İlk bellek bağlam hedef bellek bağlamı aynı kapsamı listesinde bulabilirsiniz.  
  
 CONTEXT_SAME_FUNCTION  
 İlk bellek bağlam hedef bellek kapsamı aynı işlevi listesinde bulabilirsiniz.  
  
 CONTEXT_SAME_MODULE  
 İlk bellek bağlam hedef bellek bağlamı aynı modüldeki listesinde bulabilirsiniz.  
  
 CONTEXT_SAME_PROCESS  
 İlk bellek bağlam hedef bellek bağlamı aynı işlemde listesinde bulabilirsiniz.  
  
## <a name="remarks"></a>Açıklamalar  
 Bağımsız değişken olarak geçirilen [karşılaştırmak](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md) yöntemi.  
  
 Bu değerler belirtilen karşılaştırma ölçütlerini karşılayan bir listedeki ilk bellek içeriği bulmak için kullanılır. Bellek bağlam kendisini karşı karşılaştırmak için bellek bağlamları listesi verilir `IDebugMemoryContext2::Compare` yöntemi. Karşılaştırma işleci olduğu listesindeki ilk bellek bağlamda `true` sonra döndürülür.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Karşılaştırma](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)