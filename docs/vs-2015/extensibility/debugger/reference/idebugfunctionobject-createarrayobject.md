---
title: IDebugFunctionObject::CreateArrayObject | Microsoft Docs
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
- IDebugFunctionObject::CreateArrayObject
helpviewer_keywords:
- IDebugFunctionObject::CreateArrayObject method
ms.assetid: a380e53c-15f1-401f-927f-f366eea789e6
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f996e7b58150f1340bf7a47790696a54f4cbc7fa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630208"
---
# <a name="idebugfunctionobjectcreatearrayobject"></a>IDebugFunctionObject::CreateArrayObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugFunctionObject::CreateArrayObject](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfunctionobject-createarrayobject).  
  
Bir dizi nesnesi oluşturur. Bu dizi ya da temel içeren ya da örnek değerleri nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT CreateArrayObject(   
   OBJECT_TYPE    ot,  
   IDebugField*   pClassField,  
   DWORD          dwRank,  
   DWORD          dwDims[],  
   DWORD          dwLowBounds[],  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int CreateArrayObject(  
   enum_OBJECT_TYPE ot,   
   IDebugField      pClassField,   
   uint             dwRank,   
   uint[]           dwDims,   
   uint[]           dwLowBounds,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ot`  
 [in] Bir değer belirtir [Nesne_türü](../../../extensibility/debugger/reference/object-type.md) yeni bir dizi nesne türünü gösteren sabit listesi.  
  
 `pClassField`  
 [in] Bir [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) nesnenin bir dizi örnek değerleri oluşturuyorsanız bir nesnenin sınıfını temsil eden nesne. Temel nesneler dizisi oluşturuyorsanız, bu parametre null bir değerdir.  
  
 `dwRank`  
 [in] Boyut veya dizinin boyut sayısı.  
  
 `dwDims`  
 [in] Dizinin her boyutunun boyutları.  
  
 `dwLowBounds`  
 [in] Her boyutun kaynağını (genellikle 0 veya 1).  
  
 `ppObject`  
 [out] Döndürür bir [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) yeni oluşturulan diziyi temsil eden nesne. Bu, aslında bir [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md) nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Tarafından temsil edilen işlevi için bir dizi parametre temsil eden bir nesne oluşturmak için bu yöntemi çağırın [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)

