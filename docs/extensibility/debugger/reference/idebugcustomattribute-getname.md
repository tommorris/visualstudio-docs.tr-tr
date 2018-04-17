---
title: IDebugCustomAttribute::GetName | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCustomAttribute::GetName
helpviewer_keywords:
- IDebugCustomAttribute::GetName
ms.assetid: ba509cc5-5816-4925-a094-4c72d88c360c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1a33b4507cb54095a38671eaf310d87dae180be6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugcustomattributegetname"></a>IDebugCustomAttribute::GetName
Özel öznitelik adını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetName(   
   BSTR* bstrName  
);  
```  
  
```csharp  
int GetName(  
   out string bstrName  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `bstrName`  
 [out] Özel özniteliğin adını içeren bir dize döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından döndürülen adlandırılmış öznitelik bildirmek için kullanılan sınıf adına karşılık gelir. C# özel öznitelik adı bir bildiriminde kullanıldığında kesilmesini "Özniteliği" soneki izin verdiği ölçüde, bu tam bir özel öznitelik sınıfı adını karşılık gelebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)