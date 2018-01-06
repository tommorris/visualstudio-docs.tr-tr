---
title: IDebugArrayObject::GetElement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugArrayObject::GetElement
helpviewer_keywords: IDebugArrayObject::GetElement method
ms.assetid: 08b44341-7bf1-4a8c-8b79-98ae5785b195
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: dbe40cd481d3044eb87b5c5935e023bc7b110a50
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugarrayobjectgetelement"></a>IDebugArrayObject::GetElement
Dizi öğesi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
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
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Dizi nesnesi çok boyutlu olsa bile bu yöntem tüm öğeleri bir dizi nesnesinin tek boyutlu bir dizi olarak görür. Örneğin, dizi verilen `myarray[3][2][6]` ve `dwIndex` 20 parametresinin, bu yöntem döndürebildiği bir öğeyi `myarray[1][1][2]`ve bir `dwIndex` 21 parametresinin öğesinden döndürebildiği `myarray[1][1][3]`. Kullanım [GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md) dizideki öğeler toplam sayısını belirlemek için yöntem.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)