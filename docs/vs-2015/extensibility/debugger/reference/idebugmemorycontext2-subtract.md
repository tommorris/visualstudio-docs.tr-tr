---
title: IDebugMemoryContext2::Subtract | Microsoft Docs
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
- IDebugMemoryContext2::Subtract
helpviewer_keywords:
- Subtract method
- IDebugMemoryContext2::Subtract method
ms.assetid: 63df14c7-8d7e-47c1-afa7-5a1ab5d8eaba
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3265e8845340b2a02dbd5bf30c05b9e4c4d2400b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630904"
---
# <a name="idebugmemorycontext2subtract"></a>IDebugMemoryContext2::Subtract
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugMemoryContext2::Subtract](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmemorycontext2-subtract).  
  
Belirtilen değer geçerli bağlamdan çıkarır ve yeni bir bağlam döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT Subtract(   
   UINT64                 dwCount,  
   IDebugMemoryContext2** ppMemCxt  
);  
```  
  
```csharp  
int Subtract(  
   ulong                    dwCount,   
   out IDebugMemoryContext2 ppMemCxt  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwCount`  
 [in] Düşürmek için bellek bayt sayısı.  
  
 `ppMemCxt`  
 [out] Yeni bir [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir bellek bağlamı bir adresi olduğundan bir değeri bir adresinden çıkararak yeni bir bağlam arabirimi gerektiren yeni bir adres üretir.  
  
 Bu bağlamla ilişkilendirilen bellek alanını elde edilen adresi dışında olsa bile, bu yöntem her zaman yeni bir bağlam üretmesi gerekir. Yeni bağlam için ayrılan bellek yok ise veya tek özel durumu olan `ppMemCxt` (Bu bir hatadır) null bir değerdir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)

