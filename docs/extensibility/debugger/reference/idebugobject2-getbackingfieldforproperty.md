---
title: IDebugObject2::GetBackingFieldForProperty | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugObject2::GetBackingFieldForProperty
helpviewer_keywords:
- IDebugObject2::GetBackingFieldForProperty method
ms.assetid: e72c6338-5573-4fad-8075-f3ade3435424
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7729f55c93274796d3c81f280618653b873bc40b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31122515"
---
# <a name="idebugobject2getbackingfieldforproperty"></a>IDebugObject2::GetBackingFieldForProperty
Alan veya değişken (varsa) alır, yedekleme bu nesne tarafından temsil edilen özelliği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetBackingFieldForProperty(  
   IDebugObject2** ppObject  
);  
```  
  
```csharp  
int GetBackingFieldForProperty(  
   out IDebugObject2 ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppObject`  
 [out] Bir [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md) yedekleme alanını tanımlayan nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md) temsil eden bir yönetilen kod sınıfı özelliği, diğer bir deyişle, bir get yöntemiyle nesne ve/veya ayarlama erişimcisi. Gibi özellikleri genellikle özelliği tarafından yönetilebilir içermesi için bir değişken gerektirir. Bu değişken yedekleme alanı olarak bilinir. Nesne için yedekleme alanı yok ise, sonra bir null değer döndürmek emin olun: bazı arayanlar dönüş değeri dikkat değil ancak bunun yerine içinde bir null değer döndürüldü olmadığını görmek için görüneceğini `ppObject`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)