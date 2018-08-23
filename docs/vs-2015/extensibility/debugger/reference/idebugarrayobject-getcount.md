---
title: IDebugArrayObject::GetCount | Microsoft Docs
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
- IDebugArrayObject::GetCount
helpviewer_keywords:
- IDebugArrayObject::GetCount method
ms.assetid: 7931f3f7-033c-4bf8-8abd-95183952ebb0
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9442356b69be6e14e455a270287946e26604e69a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677673"
---
# <a name="idebugarrayobjectgetcount"></a>IDebugArrayObject::GetCount
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugArrayObject::GetCount](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugarrayobject-getcount).  
  
Dizideki öğe sayısını alır.  
  
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
 Başarılıysa S_OK döndürür; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Çok boyutlu dizi nesnesi olsa bile, bu yöntem, bir dizi nesnesinin tüm öğeleri tek boyutlu dizi görür. Örneğin, bir dizi verilen `myarray[3][2][6]`, bu yöntem, 36 döndürecekti `pdwElements` parametresi. Kullanım [GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md) aynı anda tek tek tek öğeleri almak için yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)

