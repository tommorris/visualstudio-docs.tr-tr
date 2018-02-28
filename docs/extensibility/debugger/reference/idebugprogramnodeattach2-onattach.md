---
title: IDebugProgramNodeAttach2::OnAttach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProgramNodeAttach2::OnAttach
helpviewer_keywords:
- IDebugProgramNodeAttach2::OnAttach
ms.assetid: 5fe52761-a508-4ab5-abdb-334fb6590334
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a6b0f74ef5b14fb9e8971c0d539cc2e875658341
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramnodeattach2onattach"></a>IDebugProgramNodeAttach2::OnAttach
İlişkili programı ekler veya ekleme işlemi için erteler [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) yöntemi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT OnAttach(  
   [in] REFGUID guidProgramId  
);  
```  
  
```csharp  
int OnAttach(  
   ref Guid guidProgramId  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 `guidProgramId`  
 [in] `GUID` ilişkili programına atamak için.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`. Döndürür `S_FALSE` varsa [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) yöntemi kullanılmamalıdır. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem attach işlemi sırasında önce çağrılır [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) yöntemi çağrılır. `OnAttach` Yöntemi ekleme işlemi gerçekleştirebilirsiniz (Bu yöntem, bu durumda `S_FALSE`) veya ekleme işlemi için erteleneceği `IDebugEngine2::Attach` yöntemi ( `OnAttach` yöntemi döndürür `S_OK`). Ya da bir olay `OnAttach` yöntemi ayarlayabilirsiniz `GUID` için ayıklanacak programının verilen `GUID`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)