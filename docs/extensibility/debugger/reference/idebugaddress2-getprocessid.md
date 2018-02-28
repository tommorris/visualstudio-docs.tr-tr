---
title: IDebugAddress2::GetProcessID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugAddress2::GetProcessID
helpviewer_keywords:
- IDebugAddress2::GetProcessID method
ms.assetid: 2c18889d-074a-4b95-87b4-bf1a067f44ed
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: bcc83bf3fd83a0c84fa73e11fc9c25f990bd769b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugaddress2getprocessid"></a>IDebugAddress2::GetProcessID
Bu tarafından temsil edilen nesne sahibi işlemin Kimliğini alır [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetProcessID (  
   DWORD* pProcID  
);  
```  
  
```csharp  
int GetProcessID (  
   out uint pProcID  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pProcID`  
 [out] İşlem kimliği.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md)