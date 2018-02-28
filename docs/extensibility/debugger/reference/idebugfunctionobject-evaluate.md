---
title: IDebugFunctionObject::Evaluate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugFunctionObject::Evaluate
helpviewer_keywords:
- IDebugFunctionObject::Evaluate method
ms.assetid: 29349ea3-d5c1-4135-aa76-ced073ab9683
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a665f5db26955db2d3879e0d37c07efd3856bf68
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugfunctionobjectevaluate"></a>IDebugFunctionObject::Evaluate
İşlev çağrılarını ve sonuçta elde edilen değer bir nesne olarak döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Evaluate(   
   IDebugObject** ppParams,  
   DWORD          dwParams,  
   DWORD          dwTimeout,  
   IDebugObject** ppResult  
);  
```  
  
```csharp  
int Evaluate(  
   IDebugObject[]   ppParams,   
   IntPtr           dwParams,   
   uint             dwTimeout,   
   out IDebugObject ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppParams`  
 [in] Bir dizi [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) giriş parametreleri temsil eden nesne. Bu parametrelerin her biri ile oluşturulmuş `Create` yöntemleri [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) arabirimi.  
  
 `dwParams`  
 [in] Parametre sayısı `ppParams` dizi.  
  
 `dwTimeout`  
 [in] Bu yöntemle geri dönmeden önce beklenecek milisaniye cinsinden en uzun süreyi belirtir. Kullanım `INFINITE` sonsuza kadar beklenecek.  
  
 `ppResult`  
 [out] Döndürür bir [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) temsil eden bir nesne olarak işlevin değeri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem kurar ve tarafından temsil edilen işlevi çağrısı yürütür [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)