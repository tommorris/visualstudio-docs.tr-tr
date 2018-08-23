---
title: IDebugObject2::GetAlias | Microsoft Docs
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
- IDebugObject2::GetAlias
helpviewer_keywords:
- IDebugObject2::GetAlias method
ms.assetid: aa6824d5-c932-42ba-8713-950e7d1fb42f
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 77cd9b8ccdb89d2a0e52cf1193dd3137780964d5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632012"
---
# <a name="idebugobject2getalias"></a>IDebugObject2::GetAlias
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugObject2::GetAlias](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugobject2-getalias).  
  
Bu nesneyle ilişkilendirilmiş diğer ada varsa alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetAlias(  
   IDebugAlias** ppAlias  
);  
```  
  
```csharp  
int GetAlias(  
   out IDebugAlias ppAlias  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppAlias`  
 [out] Döndürür bir [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md) bu nesne için bir diğer ad temsil eden nesne; Aksi takdirde, null değeri döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir nesne için bir diğer ad çağrısı ile oluşturulan [CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)   
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)

