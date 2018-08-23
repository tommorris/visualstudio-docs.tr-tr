---
title: IDebugBinder::Bind | Microsoft Docs
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
- IDebugBinder::Bind
helpviewer_keywords:
- IDebugBinder::Bind method
ms.assetid: 15a11ad7-0fcc-4e80-ae34-8a7dd7bae3c3
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e366ae8044008da51cb2064081abbdc61288ac1b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687229"
---
# <a name="idebugbinderbind"></a>IDebugBinder::Bind
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugBinder::Bind](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbinder-bind).  
  
Bu yöntem, bellek bağlamı veya sembolün geçerli değerini içeren nesneyi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT Bind(   
   IDebugObject*  pContainer,  
   IDebugField*   pField,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int Bind(  
   IDebugObject     pContainer,  
   IDebugField      pField,  
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pContainer`  
 [in] [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) tarafından başvurulan alt içeren `pField`.  
  
 `pField`  
 [in] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) temsil eden bir simge.  
  
 `ppObject`  
 [out] Döndürür `IDebugObject` sembol örneğini temsil eden.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)

