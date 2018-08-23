---
title: IDebugBinder::ResolveRuntimeType | Microsoft Docs
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
- IDebugBinder::ResolveRuntimeType
helpviewer_keywords:
- IDebugBinder::ResolveRuntimeType method
ms.assetid: 6456ab3e-1c03-4f3c-91f9-16797ab7f5e7
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e1ac794f7ba3cc3b47cf96dacde850845fd07c9e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684245"
---
# <a name="idebugbinderresolveruntimetype"></a>IDebugBinder::ResolveRuntimeType
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugBinder::ResolveRuntimeType](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbinder-resolveruntimetype).  
  
Bu yöntem, bir nesnenin çalışma zamanı türünü belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT ResolveRuntimeType(   
   IDebugObject* pObject,  
   IDebugField** ppResolved  
);  
```  
  
```csharp  
int ResolveRuntimeType(  
   IDebugObject     pObject,   
   out IDebugField  ppResolved  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pObject`  
 [in] [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) çözümlenecek.  
  
 `ppResolved`  
 [out] Olarak nesne türünü döndüren bir [IDebugField](../../../extensibility/debugger/reference/idebugfield.md).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir nesnenin çalışma zamanı türü derleme zamanında her zaman bilinmiyor. Örneğin, çok biçimlilik kullanarak, bağımsız değişken bir işleve bir button sınıfı gibi temel sınıf olarak geçirilebilir. Gerçek bağımsız değişken bir radyo düğmesi sınıfı gibi türetilmiş bir sınıf olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)

