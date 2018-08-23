---
title: IDebugMemoryBytes2::GetSize | Microsoft Docs
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
- IDebugMemoryBytes2::GetSize
helpviewer_keywords:
- IDebugMemoryBytes2::GetSize method
- GetSize method
ms.assetid: dae64c5f-5b54-40c3-b32f-ec3b16c093f7
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7b5ad9b734de92f6c3b615acb8480f324ed5f5f8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695341"
---
# <a name="idebugmemorybytes2getsize"></a>IDebugMemoryBytes2::GetSize
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugMemoryBytes2::GetSize](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmemorybytes2-getsize).  
  
Bu tarafından temsil edilen belleğin bayt cinsinden boyutunu alır [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md) nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetSize(   
   UINT64* pqwSize  
);  
```  
  
```csharp  
int GetSize(  
   out ulong pqwSize  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pqwSize`  
 [out] Boyutu bayt cinsinden bellek alanını döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)

