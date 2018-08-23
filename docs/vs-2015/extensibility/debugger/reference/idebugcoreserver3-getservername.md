---
title: IDebugCoreServer3::GetServerName | Microsoft Docs
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
- IDebugCoreServer3::GetServerName
helpviewer_keywords:
- IDebugCoreServer3::GetServerName
ms.assetid: 0fc3fcf5-d6a3-4a00-bf14-458b8645714e
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1e23b8a581668e0f8c726ac8e3b14212308e86ba
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632099"
---
# <a name="idebugcoreserver3getservername"></a>IDebugCoreServer3::GetServerName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugCoreServer3::GetServerName](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcoreserver3-getservername).  
  
Sunucu adını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetServerName(  
   BSTR* pbstrName  
);  
```  
  
```csharp  
int GetServerName(  
   out string pbstrName  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pbstrName`  
 [out] Sunucunun adını döndürür.  
  
> [!NOTE]
>  Dize boşaltma için çağıran sorumludur.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi halde hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Kolay sunucu adı için şunu çağırın [GetServerFriendlyName](../../../extensibility/debugger/reference/idebugcoreserver3-getserverfriendlyname.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)   
 [GetServerFriendlyName](../../../extensibility/debugger/reference/idebugcoreserver3-getserverfriendlyname.md)

