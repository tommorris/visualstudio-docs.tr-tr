---
title: IDebugObject::SetValue | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugObject::SetValue
helpviewer_keywords:
- IDebugObject::SetValue method
ms.assetid: d652e09c-cdc1-4519-8116-d7c743f5679b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ae6f8f589c0dca8c97e1a9664d9eaa93bf9e8741
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugobjectsetvalue"></a>IDebugObject::SetValue
Ardışık bayt serisinden nesnenin değerini ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT SetValue(   
   BYTE* pValue,  
   UINT  nSize  
);  
```  
  
```csharp  
int SetValue(  
   byte[] pValue,   
   uint   nSize  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pValue`  
 [in] Yeni değer temsil eden bir bayt dizisi.  
  
 `nSize`  
 [in] Değer bayt cinsinden boyutu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Dizideki bu kopyalanır [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) tüm mevcut değerini değiştirerek nesnesi. Yeni değer boyutu mevcut değeri daha büyük veya küçük olabilir. Bu `IDebugObject` bir null başvuru olamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)