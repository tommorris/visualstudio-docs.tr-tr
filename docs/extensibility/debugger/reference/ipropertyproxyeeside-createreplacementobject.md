---
title: IPropertyProxyEESide::CreateReplacementObject | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IPropertyProxyEESide::CreateReplacementObject
helpviewer_keywords:
- IPropertyProxyEESide::CreateReplacementObject
ms.assetid: 0cfe79b8-c3f1-48b0-a225-e39dee2c92fe
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 56e5001d7abd498982361a51d0386db4b2624cf7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31135623"
---
# <a name="ipropertyproxyeesidecreatereplacementobject"></a>IPropertyProxyEESide::CreateReplacementObject
İfade değerlendiricisi (EE) için belirli bir veri nesnesi bir kopyasını oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT CreateReplacementObject(  
   IEEDataStorage*  dataIn,  
   IEEDataStorage** dataOut  
);  
```  
  
```csharp  
int CreateReplacementObject(  
   IEEDataStorage     dataIn,  
   out IEEDataStorage dataOut  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dataIn`  
 [in] Bir [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) kopyalanacak verileri tutan nesne.  
  
 `dataOut`  
 [out] Yeni bir döndürür `IEEDataStorage` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem verilen bir [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) bir bayt dizisi temsil eden nesne. Bu gelen veri nesnesi tarafından EE genellikle uygulanmadı. Ancak, bu yöntem tarafından döndürülen nesne EE uygulama sağlayan EE tarafından her zaman uygulanır `IEEDataStorage` ne olursa olsun sınıfı istenen üzerinde arabirimi.  
  
 Veri gelen tarafından sağlanan Not `IEEDataStorage` nesne giden aynı verileri olmalıdır `IEEDataStorage` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)