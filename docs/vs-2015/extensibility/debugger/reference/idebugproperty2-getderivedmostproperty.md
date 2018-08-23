---
title: IDebugProperty2::GetDerivedMostProperty | Microsoft Docs
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
- IDebugProperty2::GetDerivedMostProperty
helpviewer_keywords:
- IDebugProperty2::GetDerivedMostProperty
ms.assetid: cc86b461-62d1-4340-8209-c65037fd8b02
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 32581e352b3f3862da326638e1645c2ad117f5ad
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686655"
---
# <a name="idebugproperty2getderivedmostproperty"></a>IDebugProperty2::GetDerivedMostProperty
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProperty2::GetDerivedMostProperty](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugproperty2-getderivedmostproperty).  
  
Bir özelliğin türetilmiş çoğu özelliği alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetDerivedMostProperty (   
   IDebugProperty2** ppDerivedMost  
);  
```  
  
```csharp  
int GetDerivedMostProperty (   
   out IDebugProperty2 ppDerivedMost  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppDerivedMost`  
 [out] Döndürür bir [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) türetilmiş çoğu özelliği temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi halde hata kodu döndürür. Döndürür `S_GETDERIVEDMOST_NO_DERIVED_MOST` almak için türetilmiş çoğu özelliği yok ise.  
  
## <a name="remarks"></a>Açıklamalar  
 Örneğin, bu özelliği uygulayan bir nesne tanımlar `ClassRoot` ancak aslında örneklemesi olduğu `ClassDerived` sınıfından türetilen `ClassRoot`, sonra da bu yöntemi döndürür bir [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) nesnesi açıklayan `ClassDerived` nesne.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)

