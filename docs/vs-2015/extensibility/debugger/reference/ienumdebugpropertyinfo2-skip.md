---
title: IEnumDebugPropertyInfo2::Skip | Microsoft Docs
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
- IEnumDebugPropertyInfo2::Skip
helpviewer_keywords:
- IEnumDebugPropertyInfo2::Skip
ms.assetid: 0366c778-18eb-4065-a452-64b70c751a58
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0faff874d329c7bccebea709ab4964b0f7977946
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690635"
---
# <a name="ienumdebugpropertyinfo2skip"></a>IEnumDebugPropertyInfo2::Skip
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IEnumDebugPropertyInfo2::Skip](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugpropertyinfo2-skip).  
  
Belirtilen sayıda öğeyi üzerinden atlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT Skip(  
   ULONG celt  
);  
```  
  
```csharp  
int Skip(  
   uint celt  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `celt`  
 [in] Geçilecek öğelerin sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`. Döndürür `S_FALSE` varsa `celt` kalan öğeleri sayısından büyüktür; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `celt` numarasından daha büyük bir değer belirtir, kalan öğeleri numaralandırma sonuna ayarlanır ve `S_FALSE` döndürülür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)

