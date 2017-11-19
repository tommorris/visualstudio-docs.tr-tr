---
title: IDebugObject::GetManagedDebugObject | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugObject::GetManagedDebugObject
helpviewer_keywords: IDebugObject::GetManagedDebugObject method
ms.assetid: cb89692e-7657-47ff-846d-311943521951
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a01823a2409b15ba101ad4b55d5584e385872574
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugobjectgetmanageddebugobject"></a>IDebugObject::GetManagedDebugObject
Hata ayıklama altyapısı adres alanında yönetilen nesnesinin bir kopyasını oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetManagedDebugObject(   
   IDebugManagedObject** ppObject  
);  
```  
  
```csharp  
int GetManagedDebugObject(  
   out IDebugManagedObject ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppObject`  
 [out] Döndürür bir [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md) yeni oluşturulan yönetilen nesneyi temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür. Bu E_FAIL döndürür [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) yönetilen değer sınıfı örneğini temsil etmiyor.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) nesne gerekir temsil eden bir yönetilen değer sınıfı örneğini gibi bir `System.Decimal` örneği. Arama yükü yerel bir kopya sahip [değerlendir](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md) ortadan kalkar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)