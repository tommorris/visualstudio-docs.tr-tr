---
title: IDebugManagedObject::SetFromManagedObject | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugManagedObject::SetFromManagedObject
helpviewer_keywords: IDebugManagedObject::SetFromManagedObject method
ms.assetid: 8700ee8d-2704-4580-bccc-046837a24edd
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: da0526c060175a6e00a7b45a7ef2e347dba0d89e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmanagedobjectsetfrommanagedobject"></a>IDebugManagedObject::SetFromManagedObject
Bir parametre olarak sağlanan değer sınıfı örnekten değer sınıfı nesnesinin örneğini değerini ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT SetFromManagedObject(   
   IUnknown* pManagedObject  
);  
```  
  
```csharp  
int SetFromManagedObject(  
   object pManagedObject  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pManagedObject`  
 [in] Yeni bir değer içeren Yönetilen Nesne temsil eden bir arabirim.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem yönetilen nesne tarafından belirtildiği şekilde değiştirmek için kullanılan [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md) nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)