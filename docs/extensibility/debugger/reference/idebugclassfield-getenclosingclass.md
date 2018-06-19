---
title: IDebugClassField::GetEnclosingClass | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugClassField::GetEnclosingClass
helpviewer_keywords:
- IDebugClassField::GetEnclosingClass method
ms.assetid: a0c12e3c-9ea0-4dfb-9e45-8cea18725022
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6cd73955835f8aff0047995a690da03e5ab0305d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31105833"
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