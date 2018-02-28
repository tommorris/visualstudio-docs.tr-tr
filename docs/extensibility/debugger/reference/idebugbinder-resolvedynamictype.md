---
title: IDebugBinder::ResolveDynamicType | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugBinder::ResolveDynamicType
helpviewer_keywords:
- IDebugBinder::ResolveDynamicType method
ms.assetid: 2c36ef92-5b44-4cfd-988e-54a2e5a6710c
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: b1a6da92ae88939303d8d16cc401c152ecfb0c36
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugbinderresolvedynamictype"></a>IDebugBinder::ResolveDynamicType
Bu yöntem, tam bir değişken türünü döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT ResolveDynamicType (  
   IDebugDynamicField *pDynamic,  
   IDebugField       **ppResolved  
);  
```  
  
```csharp  
int ResolveDynamicType(  
   IDebugDynamicField pDynamic,   
   out IDebugField    ppResolved  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pDynamic`  
 [in] Bir [IDebugDynamicField](../../../extensibility/debugger/reference/idebugdynamicfield.md) temsil eden bir değişken türü.  
  
 `ppResolved`  
 [out] Döndürür bir [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) değişkenin türü hakkındaki belirli bilgileri verir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IDebugDynamicField](../../../extensibility/debugger/reference/idebugdynamicfield.md)