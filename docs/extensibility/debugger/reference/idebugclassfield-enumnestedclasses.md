---
title: IDebugClassField::EnumNestedClasses | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugClassField::EnumNestedClasses
helpviewer_keywords:
- IDebugClassField::EnumNestedClasses method
ms.assetid: 2ba5ef0c-395e-4006-9e3c-9b06e1d711d0
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 90a8b7fd2767ca3d7b122a65bf12bf6aed7f17bb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugclassfieldenumnestedclasses"></a>IDebugClassField::EnumNestedClasses
Bu sınıf iç içe geçmiş sınıflar için bir numaralandırıcı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT EnumNestedClasses(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumNestedClasses(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppEnum`  
 [out] Döndürür bir [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) iç içe geçmiş sınıflar listesini temsil eden nesne. Hiçbir iç içe geçmiş sınıflar yoksa null değeri döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK döndürür veya hiç iç içe geçmiş sınıflar varsa S_FALSE döndürür. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Numaralandırma her öğenin bir [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) iç içe geçmiş sınıf tanımlayan nesne.  
  
 İç içe geçmiş sınıf başka bir sınıf içinde tanımlanan bir sınıftır. Örneğin:  
  
```  
class RootClass {  
   class NestedClass { }  
};  
```  
  
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) numaralandırma, bir nesneyi temsil eden içerecektir `NestedClass` sınıfı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)