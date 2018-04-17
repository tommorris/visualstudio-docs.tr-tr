---
title: IDebugMethodField::EnumAllLocals | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMethodField::EnumAllLocals
helpviewer_keywords:
- IDebugMethodField::EnumAllLocals method
ms.assetid: 0bc7cc13-2628-4bd8-8c06-4d2aa6755ea8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8c3c13f7252e6f3b662ded697ab267419fd66450
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugmethodfieldenumalllocals"></a>IDebugMethodField::EnumAllLocals
Yönteminin Dahili derleyici tarafından üretilen dahil olmak üzere tüm yerel değişkenler için bir numaralandırıcı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT EnumAllLocals(   
   IDebugAddress*     pAddress,  
   IEnumDebugFields** ppLocals  
);  
```  
  
```csharp  
int EnumAllLocals(  
   IDebugAddress        pAddress,   
   out IEnumDebugFields ppLocals  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pAddress`  
 [in] Bir [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) belirli kapsam veya bağlamda yöntemi içinde bir hata ayıklama adresini temsil eden nesne.  
  
 `ppLocals`  
 [out] Döndüren bir [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) belirtilen kapsamdaki tüm Yereller listesini temsil eden nesne; Aksi takdirde hiçbir Yereller gösteren bir null değeri döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK döndürür veya hiçbir Yereller varsa S_FALSE döndürür. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Yalnızca belirli hata ayıklama adresini içeren bloğu içinde tanımlanan değişkenler numaralandırılır. Bu yöntem herhangi derleyicinin ürettiği yerel öğeler içerir. Gereken tüm kaynak, çağrı açıkça tanımlanmış Yereller varsa [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md) yöntemi.  
  
 Bir yöntemi, birden çok kapsam bağlamları veya blokları içerebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)