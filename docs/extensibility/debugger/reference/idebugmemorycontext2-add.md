---
title: IDebugMemoryContext2::Add | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMemoryContext2::Add
helpviewer_keywords:
- IDebugMemoryContext2::Add method
- Add method
ms.assetid: 3c47e646-ce9e-4dd3-8f1a-6dbd3827d407
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 40ec185caf65197d46abc7def26def7929f70d74
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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