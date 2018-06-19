---
title: IDebugMemoryContext2::Add | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMemoryContext2::Add
helpviewer_keywords:
- IDebugMemoryContext2::Add method
- Add method
ms.assetid: 3c47e646-ce9e-4dd3-8f1a-6dbd3827d407
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ad55b81c1c4126efd69779e929521cfb94235ccc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31111940"
---
# <a name="idebugmemorycontext2add"></a>IDebugMemoryContext2::Add
Belirtilen değer geçerli Bağlamla ekler ve yeni bir bağlam döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Add(   
   UINT64                 dwCount,  
   IDebugMemoryContext2** ppMemCxt  
);  
```  
  
```csharp  
int Add(  
   ulong                    dwCount,   
   out IDebugMemoryContext2 ppMemCxt  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwCount`  
 [in] Geçerli bağlamda eklenecek değer.  
  
 `ppMemCxt`  
 [out] Yeni bir döndürür [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bellek bağlamı bir adresi olduğundan, bir adresi için bir değer ekleyerek yeni bir bağlam arabirimi gerektirir yeni bir adres oluşturur.  
  
 Bu bağlamla ilişkili bellek alanı dışında elde edilen adresi olsa bile, bu yöntem her zaman yeni bir bağlam üretmek gerekir. Yeni bağlam için ayrılan bellek yok ya da tek özel durum olan `ppMemCxt` (bir hata olan) bir null değer.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)