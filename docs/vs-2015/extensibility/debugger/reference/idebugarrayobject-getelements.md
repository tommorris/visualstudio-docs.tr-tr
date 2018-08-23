---
title: IDebugArrayObject::GetElements | Microsoft Docs
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
- IDebugArrayObject::GetElements
helpviewer_keywords:
- IDebugArrayObject::GetElements method
ms.assetid: f6a6262f-5183-46ce-8a45-33ef46088b98
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 16e4ce5b705d55203a0c9b7da02655be91628064
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694865"
---
# <a name="idebugarrayobjectgetelements"></a>IDebugArrayObject::GetElements
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugArrayObject::GetElements](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugarrayobject-getelements).  
  
Dizinin tüm öğelerinin bir numaralandırıcıyı alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetElements(   
   IEnumDebugObjects** ppEnum  
);  
```  
  
```csharp  
int GetElements(  
   out IEnumDebugObjects ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppEnum`  
 [out] Döndürür bir [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md) tüm öğelerini numaralandırma sağlayan nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Alternatif olarak, kullanın [GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md) ve [GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md) öğeler boyunca yineleme yapmak için yöntemleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)

