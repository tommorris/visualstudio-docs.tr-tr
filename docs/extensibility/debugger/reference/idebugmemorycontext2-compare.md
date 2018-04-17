---
title: IDebugMemoryContext2::Compare | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMemoryContext2::Compare
helpviewer_keywords:
- IDebugMemoryContext2::Compare method
- Compare method
ms.assetid: c51b5128-848e-4d8e-b2e9-1161339763c3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b9c72120a4153ed6d0d19a2cf2b7d3a9a9943801
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugmemorycontext2compare"></a>IDebugMemoryContext2::Compare
Verilen dizi eşleşen ilk içerik dizinini döndürme karşılaştırma bayrakları tarafından belirtildiği şekilde her bağlamda bellek bağlamına karşılaştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Compare(   
   CONTEXT_COMPARE        compare,  
   IDebugMemoryContext2** rgpMemoryContextSet,  
   DWORD                  dwMemoryContextSetLen,  
   DWORD*                 pdwMemoryContext  
);  
```  
  
```csharp  
int Compare(  
   enum_CONTEXT_COMPARE   compare,   
   IDebugMemoryContext2[] rgpMemoryContextSet,   
   uint                   dwMemoryContextSetLen,   
   out uint               pdwMemoryContext  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `compare`  
 [in] Arasında bir değer [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md) karşılaştırma türünü belirleyen numaralandırması.  
  
 `rgpMemoryContextSet`  
 [in] Bir dizi başvurular [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) Karşılaştırılacak nesne.  
  
 `dwMemoryContextSetLen`  
 [in] Bağlamlarda sayısı `rgpMemoryContextSet` dizi.  
  
 `pdwMemoryContext`  
 [out] Karşılaştırmayı ilk bellek içerik dizinini döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Döndürür `E_COMPARE_CANNOT_COMPARE` iki bağlamları karşılaştırılamaz durumunda.  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklama altyapısı (DE) karşılaştırmaları tüm türlerini desteklemek mevcut değil, ancak en az desteklemelidir `CONTEXT_EQUAL`, `CONTEXT_LESS_THAN`, `CONTEXT_GREATER_THAN` ve `CONTEXT_SAME_SCOPE`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)   
 [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md)