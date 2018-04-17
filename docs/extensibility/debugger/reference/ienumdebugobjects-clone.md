---
title: IEnumDebugObjects::Clone | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEnumDebugObjects::Clone
helpviewer_keywords:
- IEnumDebugObjects::Clone method
ms.assetid: cb7df109-d29a-4218-b900-6809091459dd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6e68d2a1b2b859d7a6c9872a9139ae173f0fc3f9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ienumdebugobjectsclone"></a>IEnumDebugObjects::Clone
Bu yöntem bir kopyasını ayrı bir nesne olarak geçerli numaralandırması döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Clone(  
   IEnumDebugObjects** ppEnum  
);  
```  
  
```csharp  
int Clone(  
   out IEnumDebugObjects ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppEnum`  
 [out] Bu numaralandırma ayrı bir nesne gibi bir kopyasını döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Numaralandırma kopyasını bu yöntem çağrılır aynı anda özgün ile aynı duruma sahiptir. Ancak, kopyanın ve özgün 's durumları ayrıdır ve tek tek değiştirilebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)