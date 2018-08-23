---
title: IDebugMemoryContext2::Compare | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugMemoryContext2::Compare
helpviewer_keywords:
- IDebugMemoryContext2::Compare method
- Compare method
ms.assetid: c51b5128-848e-4d8e-b2e9-1161339763c3
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4219994deb0490533207907d809e970d0fb303cf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632017"
---
# <a name="idebugmemorycontext2compare"></a>IDebugMemoryContext2::Compare
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugMemoryContext2::Compare](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmemorycontext2-compare).  
  
Eşleşen ilk bağlamıyla dizinini döndüren karşılaştırma bayrakları tarafından belirtildiği şekilde belirtilen dizideki her bağlam için bellek bağlam karşılaştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 [in] Bir değer [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md) karşılaştırma türünü belirleyen sabit listesi.  
  
 `rgpMemoryContextSet`  
 [in] İçin yapılan başvuruların dizisi [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) Karşılaştırılacak nesne.  
  
 `dwMemoryContextSetLen`  
 [in] Bağlamlarda sayısını `rgpMemoryContextSet` dizisi.  
  
 `pdwMemoryContext`  
 [out] Karşılaştırmayı ilk bellek bağlam dizinini döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Döndürür `E_COMPARE_CANNOT_COMPARE` varsa iki bağlamları karşılaştırılamaz.  
  
## <a name="remarks"></a>Açıklamalar  
 Karşılaştırma tüm türleri desteklemek hata ayıklama altyapısı (DE) yok, ancak en az desteklemelidir `CONTEXT_EQUAL`, `CONTEXT_LESS_THAN`, `CONTEXT_GREATER_THAN` ve `CONTEXT_SAME_SCOPE`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)   
 [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md)

