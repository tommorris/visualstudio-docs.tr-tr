---
title: IDebugPortEx2::GetPortProcessId | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugPortEx2::GetPortProcessId
helpviewer_keywords:
- IDebugPortEx2::GetPortProcessId
ms.assetid: be85be66-47e6-415f-b0ca-24599aa5f13c
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 5ecc39025ce92cf2b2d230b6690ad1b7bc5896ff
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportex2getportprocessid"></a>IDebugPortEx2::GetPortProcessId
Bağlantı işlem Kimliğini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetPortProcessId (   
   DWORD* pdwProcessId  
);  
```  
  
```csharp  
int GetPortProcessId (   
   out uint pdwProcessId  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pdwProcessId`  
 [out] Bağlantı noktasının fiziksel işlem kimliği döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Win32 çalışma zamanı'nda Örneğin, bu yöntem genellikle Win32 işlevi çağırır `GetCurrentProcessId` fiziksel işlem kimliklerini almak için  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)