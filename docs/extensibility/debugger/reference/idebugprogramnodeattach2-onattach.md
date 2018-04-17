---
title: IDebugProgramNodeAttach2::OnAttach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgramNodeAttach2::OnAttach
helpviewer_keywords:
- IDebugProgramNodeAttach2::OnAttach
ms.assetid: 5fe52761-a508-4ab5-abdb-334fb6590334
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3c7c7e6f7ef640b192b7ed8c57ac87375a5ad189
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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