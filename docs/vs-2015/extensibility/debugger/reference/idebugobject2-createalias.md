---
title: IDebugObject2::CreateAlias | Microsoft Docs
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
- IDebugObject2::CreateAlias
helpviewer_keywords:
- IDebugObject2::CreateAlias method
ms.assetid: 54a05920-5d13-4f67-962b-d1a7f013dff9
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ea05dbeb3e39ab00e068539b0af0fcabf73f1d66
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688089"
---
# <a name="idebugobject2createalias"></a>IDebugObject2::CreateAlias
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugObject2::CreateAlias](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugobject2-createalias).  
  
Benzersiz bir kimliği veya bu nesne için diğer ad oluşturur veya mevcut bir diğer adı döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT CreateAlias(  
   IDebugAlias** ppAlias  
);  
```  
  
```csharp  
int CreateAlias(  
   out IDebugAlias ppAlias  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppAlias`  
 [out] Yeni (veya varolan) diğer adı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir diğer ad nesne bellekte olsa da belirli bir nesneyi temsil eden bir etikettir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)   
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)

