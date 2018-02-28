---
title: IDebugClassField::GetEnclosingClass | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugClassField::GetEnclosingClass
helpviewer_keywords:
- IDebugClassField::GetEnclosingClass method
ms.assetid: a0c12e3c-9ea0-4dfb-9e45-8cea18725022
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 440b9845ae7f3dd57b34b4ce25f48bea3aaa7e80
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugclassfieldgetenclosingclass"></a>IDebugClassField::GetEnclosingClass
Bu sınıf barındırır sınıfı alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetEnclosingClass(   
   IDebugClassField** ppClassField  
);  
```  
  
```csharp  
int GetEnclosingClass(  
   out IDebugClassField ppClassField  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppClassField`  
 [out] Döndürür bir [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) nesne kapsayan temsil eden sınıf. Kapsayan sınıfı yok ise null değeri döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfı bu tarafından temsil edilen varsa [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) nesnesidir iç içe geçmiş sınıf sonra `ppClassField` parametresi döndürür bir `IDebugClassField` nesne kapsayan temsil eden sınıf. Örneğin, bu sınıf tanımını verilen:  
  
```  
class RootClass {  
   class NestedClass { }  
};  
```  
  
 Çağırma `GetEnclosingClass` yöntemi `IDebugClassField` nesnesini temsil eden `NestedClass` sınıf döndürür bir `IDebugClassField` sınıfı temsil eden nesne `RootClass`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)