---
title: IDebugPointerObject::GetBytes | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPointerObject::GetBytes
helpviewer_keywords:
- IDebugPointerObject::GetBytes method
ms.assetid: e986c188-87fb-4b51-86e9-ee6a0035bdab
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1459a0f99dd4b0ea9c9e998404b1ffe1733cb3bf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31115872"
---
# <a name="idebugpointerobjectgetbytes"></a>IDebugPointerObject::GetBytes
Bir dizi ardışık bayt olarak işaret değerini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetBytes(   
   DWORD  dwStart,  
   DWORD  dwCount,  
   BYTE*  pBytes,  
   DWORD* pdwBytes  
);  
```  
  
```csharp  
int GetBytes(  
   uint       dwStart,   
   uint       dwCount,   
   out byte[] pBytes,   
   out uint   pdwBytes  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwStart`  
 [in] İşaret nesnesi başından bayt cinsinden uzaklık.  
  
 `dwCount`  
 [in] Alınacak bayt sayısı.  
  
 `pBytes`  
 [içinde out] Değeri bir dizi ardışık bayt olarak doldurulan bir dizi nesnesinden belirtilen uzaklığından başlayan işaret.  
  
 `pdwBytes`  
 [out] Gerçekte alınan bayt sayısını döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, kullanılır bu tarafından temsil edilen işaretçi [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md) bir ilkel türe veya ilkel türler (basit bir bayt dizisi tarafından temsil edilen bir dizi) basit bir dizi gösteriyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)   
 [SetBytes](../../../extensibility/debugger/reference/idebugpointerobject-setbytes.md)