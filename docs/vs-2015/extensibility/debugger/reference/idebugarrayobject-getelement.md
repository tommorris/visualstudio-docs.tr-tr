---
title: IDebugArrayObject::GetElement | Microsoft Docs
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
- IDebugArrayObject::GetElement
helpviewer_keywords:
- IDebugArrayObject::GetElement method
ms.assetid: 08b44341-7bf1-4a8c-8b79-98ae5785b195
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b02e13443735b2f4620c479495c8aab8af9b3108
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630551"
---
# <a name="idebugarrayobjectgetelement"></a>IDebugArrayObject::GetElement
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugArrayObject::GetElement](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugarrayobject-getelement).  
  
Bir dizideki öğe alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetElement(   
   DWORD          dwIndex,  
   IDebugObject** ppElement  
);  
```  
  
```csharp  
int GetElement(  
   [In] uint dwIndex,   
   out IDebugObject ppElement  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwIndex`  
 [in] Öğenin dizini.  
  
 `ppElement`  
 [out] Döndürür bir [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) öğeyi temsil eden arabirim.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Çok boyutlu dizi nesnesi olsa bile, bu yöntem, bir dizi nesnesinin tüm öğeleri tek boyutlu dizi görür. Örneğin, bir dizi verilen `myarray[3][2][6]` ve `dwIndex` 20 parametresi, bu yöntem döndürmesine öğesinden `myarray[1][1][2]`ve bir `dwIndex` 21 parametresinin öğesinden döndürmesine `myarray[1][1][3]`. Kullanım [GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md) dizideki öğelerin toplam sayısını belirlemek için yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)

