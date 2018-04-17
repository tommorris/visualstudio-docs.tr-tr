---
title: IDebugFunctionObject::CreateArrayObject | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugFunctionObject::CreateArrayObject
helpviewer_keywords:
- IDebugFunctionObject::CreateArrayObject method
ms.assetid: a380e53c-15f1-401f-927f-f366eea789e6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 39695d37012f90d7e61c04f64ee1c05f11482373
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugfunctionobjectcreatearrayobject"></a>IDebugFunctionObject::CreateArrayObject
Bir dizi nesnesi oluşturur. Bu dizi ya da ilkel içeren veya örnek değerleri nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT CreateArrayObject(   
   OBJECT_TYPE    ot,  
   IDebugField*   pClassField,  
   DWORD          dwRank,  
   DWORD          dwDims[],  
   DWORD          dwLowBounds[],  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int CreateArrayObject(  
   enum_OBJECT_TYPE ot,   
   IDebugField      pClassField,   
   uint             dwRank,   
   uint[]           dwDims,   
   uint[]           dwLowBounds,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ot`  
 [in] Arasında bir değer belirtir [Nesne_türü](../../../extensibility/debugger/reference/object-type.md) yeni dizi nesnesi türünü gösteren numaralandırma.  
  
 `pClassField`  
 [in] Bir [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) bir dizi nesnesinin örneği değerleri oluşturuyorsanız bir nesnenin sınıfını temsil eden nesne. İlkel nesnelerinin bir dizisi oluşturuyorsanız, bu parametre null bir değerdir.  
  
 `dwRank`  
 [in] Derece veya dizinin boyut sayısını.  
  
 `dwDims`  
 [in] Dizinin her boyut boyutları.  
  
 `dwLowBounds`  
 [in] Her boyut kökeni (genellikle 0 veya 1).  
  
 `ppObject`  
 [out] Döndürür bir [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) yeni oluşturulan dizi temsil eden nesne. Bu gerçekten olan bir [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md) nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir dizi parametresi tarafından temsil edilen işlevi temsil eden bir nesne oluşturmak için bu yöntemi çağırın [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)