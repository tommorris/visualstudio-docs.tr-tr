---
title: IDebugProgram2::GetDebugProperty | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::GetDebugProperty
helpviewer_keywords:
- IDebugProgram2::GetDebugProperty
ms.assetid: d194224e-f0e6-46ab-85d4-9e2639e28946
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 49c83cb4ca1dccbdf1e28d545bdcaa711e3241a6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogram2getdebugproperty"></a>IDebugProgram2::GetDebugProperty
Programın özellikleri alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetDebugProperty(   
   IDebugProperty2** ppProperty  
);  
```  
  
```csharp  
int GetDebugProperty(   
   out IDebugProperty2 ppProperty  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppProperty`  
 [out] Döndürür bir [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) programın özellikleri temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından döndürülen özellikleri programa özgüdür. Program birden fazla özelliği döndürme gerekiyorsa sonra [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) bu yöntem tarafından döndürülen nesne ek özellikler ve arama bir kapsayıcıdır [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) yöntemi döndürür bir tüm özelliklerin listesi.  
  
 Bir program herhangi sayısı ve türü aracılığıyla açıklanan ek özellikler getirebilir `IDebugProperty2` arabirimi. Bir IDE genel özellik tarayıcı kullanıcı arabirimi aracılığıyla ek program özelliklerini görüntüleyebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)