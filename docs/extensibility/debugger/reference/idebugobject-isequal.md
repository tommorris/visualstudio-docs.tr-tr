---
title: IDebugObject::IsEqual | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugObject::IsEqual
helpviewer_keywords: IDebugObject::IsEqual method
ms.assetid: 4b76e663-ef2e-41ff-9be1-bf26d666a34a
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5d5fd33bf626fe04159ac5bae12c586776ac334e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugobjectisequal"></a>IDebugObject::IsEqual
Bu nesne bir nesneyle karşılaştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT IsEqual(   
   IDebugObject* pObject,  
   BOOL*         pfIsEqual  
);  
```  
  
```csharp  
int IsEqual(  
   IDebugObject pObject,  
   out int      pfIsEqual  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pObject`  
 [in] Bir [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) karşılaştırmak üzere nesnesini temsil eden nesne.  
  
 `pfIsEqual`  
 [out] Sıfır olmayan döndürür (`TRUE`) tersi nesneleri değerleri ise sıfır döndürür (`FALSE`).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Genellikle, bu yöntem tarafından temsil edilen değerler adreslerini karşılaştırabilirsiniz `pObject` parametresi ve bu [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) nesne; adresleri eşit sonra nesnelerin eşit olarak düşünülebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)