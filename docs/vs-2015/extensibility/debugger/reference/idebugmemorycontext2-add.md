---
title: IDebugMemoryContext2::Add | Microsoft Docs
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
- IDebugMemoryContext2::Add
helpviewer_keywords:
- IDebugMemoryContext2::Add method
- Add method
ms.assetid: 3c47e646-ce9e-4dd3-8f1a-6dbd3827d407
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 47fe65ae76f60026f08d18ce17fc48e22885e042
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630421"
---
# <a name="idebugmemorycontext2add"></a>IDebugMemoryContext2::Add
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugMemoryContext2::Add](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmemorycontext2-add).  
  
Belirtilen değer için geçerli bağlam ekler ve yeni bir bağlam döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 [in] Geçerli bağlama eklemek için değer.  
  
 `ppMemCxt`  
 [out] Yeni bir [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir bellek bağlamı bir adresi olduğundan bir adrese bir değeri ekleyerek yeni bir bağlam arabirimi gerektiren yeni bir adres üretir.  
  
 Bu bağlamla ilişkilendirilen bellek alanını elde edilen adresi dışında olsa bile, bu yöntem her zaman yeni bir bağlam üretmesi gerekir. Yeni bağlam için ayrılan bellek yok ise veya tek özel durumu olan `ppMemCxt` (Bu bir hatadır) null bir değerdir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)

