---
title: IDebugPointerObject::SetBytes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugPointerObject::SetBytes
helpviewer_keywords:
- IDebugPointerObject::SetBytes method
ms.assetid: 8c578b38-38d7-46f3-bb2e-8a730fccd334
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9bab2459d2de40fdc3ea44fe7e5e92c138a5f006
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugpointerobjectsetbytes"></a>IDebugPointerObject::SetBytes
Bir dizi ardışık bayt işaret değerini ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT SetBytes(   
   DWORD  dwStart,  
   DWORD  dwCount,  
   BYTE*  pBytes,  
   DWORD* pdwBytes  
);  
```  
  
```csharp  
int SetBytes(  
   uint     dwStart,   
   uint     dwCount,   
   byte[]   pBytes,   
   out uint pdwBytes  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwStart`  
 [in] İşaret nesnesi başından bayt cinsinden uzaklık.  
  
 `dwCount`  
 [in] Ayarlamak için bayt sayısı.  
  
 `pBytes`  
 [in] Yeni değer temsil eden bir bayt dizisi. Bu değer, verilen uzaklıkta başlayan nesne içinde depolanır.  
  
 `pdwBytes`  
 [out] Bayt sayısı gerçekte kümesi getirir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, kullanılır bu tarafından temsil edilen işaretçi [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md) bir ilkel türe veya ilkel türler (basit bir bayt dizisi tarafından temsil edilen bir dizi) basit bir dizi gösteriyor. Bu `IDebugPointerObject` nesne (bunu işaret etmelidir bellekteki bir adresi) bir null başvuru olamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [GetBytes](../../../extensibility/debugger/reference/idebugpointerobject-getbytes.md)   
 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)