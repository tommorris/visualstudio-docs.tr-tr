---
title: IDebugProperty2::GetReference | Microsoft Docs
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
- IDebugProperty2::GetReference
helpviewer_keywords:
- IDebugProperty2::GetReference method
ms.assetid: 2fa97d9b-c3d7-478e-ba5a-a933f40a0103
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 22d187fb8e5f3c2fd869de5f6472d0e761dd8c8e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633470"
---
# <a name="idebugproperty2getreference"></a>IDebugProperty2::GetReference
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProperty2::GetReference](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugproperty2-getreference).  
  
Özelliğin değerine bir başvuru döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetReference(  
   IDebugReference2** ppReference  
);  
```  
  
```csharp  
int GetReference(  
   out IDebugReference2 ppReference  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppRererence`  
 [out] Döndürür bir [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) özelliğinin değeri için bir başvuruyu temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde, genellikle bir hata kodu döndürür `E_NOTIMPL` veya `E_GETREFERENCE_NO_REFERENCE`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)

