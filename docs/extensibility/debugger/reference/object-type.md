---
title: "NESNE_TÜRÜ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OBJECT_TYPE
helpviewer_keywords: OBJECT_TYPE enumeration
ms.assetid: c4d246f9-8a98-44ec-b2bb-ff5c684f668e
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 223833857568da64e24aa2e955ecabce0b36af57
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="objecttype"></a>OBJECT_TYPE
İfade değerlendirici nesneden türünü belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_OBJECT_TYPE {   
   OBJECT_TYPE_BOOLEAN = 0x0,  
   OBJECT_TYPE_CHAR    = 0x1,  
   OBJECT_TYPE_I1      = 0x2,  
   OBJECT_TYPE_U1      = 0x3,  
   OBJECT_TYPE_I2      = 0x4,  
   OBJECT_TYPE_U2      = 0x5,  
   OBJECT_TYPE_I4      = 0x6,  
   OBJECT_TYPE_U4      = 0x7,  
   OBJECT_TYPE_I8      = 0x8,  
   OBJECT_TYPE_U8      = 0x9,  
   OBJECT_TYPE_R4      = 0xa,  
   OBJECT_TYPE_R8      = 0xb,  
   OBJECT_TYPE_OBJECT  = 0xc,  
   OBJECT_TYPE_NULL    = 0xd,  
   OBJECT_TYPE_CLASS   = 0xe  
};  
typedef DWORD OBJECT_TYPE;  
```  
  
```csharp  
public enum enum_OBJECT_TYPE {   
   OBJECT_TYPE_BOOLEAN = 0x0,  
   OBJECT_TYPE_CHAR    = 0x1,  
   OBJECT_TYPE_I1      = 0x2,  
   OBJECT_TYPE_U1      = 0x3,  
   OBJECT_TYPE_I2      = 0x4,  
   OBJECT_TYPE_U2      = 0x5,  
   OBJECT_TYPE_I4      = 0x6,  
   OBJECT_TYPE_U4      = 0x7,  
   OBJECT_TYPE_I8      = 0x8,  
   OBJECT_TYPE_U8      = 0x9,  
   OBJECT_TYPE_R4      = 0xa,  
   OBJECT_TYPE_R8      = 0xb,  
   OBJECT_TYPE_OBJECT  = 0xc,  
   OBJECT_TYPE_NULL    = 0xd,  
   OBJECT_TYPE_CLASS   = 0xe  
};  
```  
  
## <a name="members"></a>Üyeler  
 OBJECT_TYPE_BOOLEAN  
 Nesne bir Boole değeri gösterir.  
  
 OBJECT_TYPE_CHAR  
 Nesne bir karakter olduğunu gösterir.  
  
 OBJECT_TYPE_I1  
 Nesne tek baytlık imzalı bir tamsayı olduğunu gösterir.  
  
 OBJECT_TYPE_U1  
 Nesne tek baytlık bir işaretsiz tamsayı olduğunu gösterir.  
  
 OBJECT_TYPE_I2  
 Nesne iki baytlık imzalı bir tamsayı olduğunu gösterir.  
  
 OBJECT_TYPE_U2  
 Nesne iki baytlık bir işaretsiz tamsayı olduğunu gösterir.  
  
 OBJECT_TYPE_I4  
 Nesne dört baytlık imzalı bir tamsayı olduğunu gösterir.  
  
 OBJECT_TYPE_U4  
 Nesne dört baytlık bir işaretsiz tamsayı olduğunu gösterir.  
  
 OBJECT_TYPE_I8  
 Nesne sekiz baytlık imzalı tamsayı olduğunu gösterir.  
  
 OBJECT_TYPE_U8  
 Nesne sekiz baytlık bir işaretsiz tamsayı olduğunu gösterir.  
  
 OBJECT_TYPE_R4  
 Nesne dört-bayt kayan noktalı sayı olduğunu gösterir.  
  
 OBJECT_TYPE_R8  
 Nesne sekiz-bayt kayan noktalı sayı olduğunu gösterir.  
  
 OBJECT_TYPE_OBJECT  
 Nesne bir nesne olduğunu gösterir.  
  
 OBJECT_TYPE_NULL  
 Nesne NULL olduğunu gösterir.  
  
 OBJECT_TYPE_CLASS  
 Nesne bir sınıf olduğunu belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bağımsız değişken olarak geçirilen [CreatePrimitiveObject](../../../extensibility/debugger/reference/idebugfunctionobject-createprimitiveobject.md) ve [CreateArrayObject](../../../extensibility/debugger/reference/idebugfunctionobject-createarrayobject.md) yöntemleri.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [CreatePrimitiveObject](../../../extensibility/debugger/reference/idebugfunctionobject-createprimitiveobject.md)   
 [CreateArrayObject](../../../extensibility/debugger/reference/idebugfunctionobject-createarrayobject.md)