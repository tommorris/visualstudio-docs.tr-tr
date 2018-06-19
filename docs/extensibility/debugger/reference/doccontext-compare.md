---
title: DOCCONTEXT_COMPARE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DOCCONTEXT_COMPARE
helpviewer_keywords:
- DOCCONTEXT_COMPARE enumeration
ms.assetid: ed947c34-b07e-4b69-8381-b6e7cb842862
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 966d31889d7979732af20f5e3f95546e87af6598
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31103659"
---
# <a name="doccontextcompare"></a>DOCCONTEXT_COMPARE
İki belge bağlamları karşılaştırma ölçütlerini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
typedef DWORD DOCCONTEXT_COMPARE;  
```  
  
```csharp  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
```  
  
## <a name="members"></a>Üyeler  
 DOCCONTEXT_EQUAL  
 Hedef belge bağlamına eşittir listedeki ilk belge bağlam bulun.  
  
 DOCCONTEXT_LESS_THAN  
 Hedef belge bağlamı'dan küçük listedeki ilk belge bağlam bulun.  
  
 DOCCONTEXT_GREATER_THAN  
 Hedef belge bağlamı büyük listesinde ilk belge bağlam bulur.  
  
 DOCCONTEXT_SAME_DOCUMENT  
 İlk belge bağlam hedef belge bağlamı aynı belgedeki listesinde bulabilirsiniz.  
  
## <a name="remarks"></a>Açıklamalar  
 Bağımsız değişken olarak geçirilen [karşılaştırmak](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md) yöntemi.  
  
 Bu değerler, listedeki ilk belge içeriği bulmak için bir karşılaştırma ölçütü belirtmek için kullanılır. Bir belge bağlamı belge bağlamları listesini kendisini karşı karşılaştırmak için verilen `IDebugDocumentContext2::Compare` yöntemi. Karşılaştırma işleci olduğu listesindeki ilk belge bağlamda `true` sonra döndürülür.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Karşılaştırma](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)