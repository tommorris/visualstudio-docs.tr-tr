---
title: IDebugArrayObject2::HasBaseIndices | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HasBaseIndices
- IDebugArrayObject2::HasBaseIndices
ms.assetid: 51a5d145-ea53-422c-b5cf-c800cf64b8e6
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 790016f356821d8e138a581c49f3c55de25b4f9d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687316"
---
# <a name="idebugarrayobject2hasbaseindices"></a>IDebugArrayObject2::HasBaseIndices
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugArrayObject2::HasBaseIndices](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugarrayobject2-hasbaseindices).  
  
Dizi tanımlı temel dizin (alt sınırı) olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT HasBaseIndices (  
   BOOL* pfHasBaseIndices  
);  
```  
  
```csharp  
int HasBaseIndices (  
   out bool pfHasBaseIndices  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pfHasBaseIndices`  
 [out] Bir dizi temel dizin (alt sınırı); olduğunu belirtmek için TRUE Aksi takdirde FALSE.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.

