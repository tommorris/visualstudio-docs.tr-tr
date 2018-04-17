---
title: IDebugArrayObject::GetCount | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugArrayObject::GetCount
helpviewer_keywords:
- IDebugArrayObject::GetCount method
ms.assetid: 7931f3f7-033c-4bf8-8abd-95183952ebb0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 81788423523837b6e8b29a8869abca7b393cf37a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugarrayobjectgetcount"></a>IDebugArrayObject::GetCount
Dizide öğe sayısını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[C++]  
HRESULT GetCount(   
   DWORD* pdwElements  
);  
```  
  
```  
[C#]  
int GetCount(  
   out uint pdwElements  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pdwElements`  
 [out] Sayımını döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Dizi nesnesi çok boyutlu olsa bile bu yöntem tüm öğeleri bir dizi nesnesinin tek boyutlu bir dizi olarak görür. Örneğin, dizi verilen `myarray[3][2][6]`, bu yöntem, 36 döndürecektir `pdwElements` parametresi. Kullanım [GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md) ayrı ayrı öğeler tek bir kerede alma yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)