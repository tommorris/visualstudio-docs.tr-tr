---
title: IDebugFunctionObject::CreateObject | Microsoft Docs
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
- IDebugFunctionObject::CreateObject
helpviewer_keywords:
- IDebugFunctionObject::CreateObject method
ms.assetid: c4c99dd5-609a-4e7c-8f29-eb728f57e995
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cf76bc294fd1b9733a6ee143748da470269f0356
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689724"
---
# <a name="idebugfunctionobjectcreateobject"></a>IDebugFunctionObject::CreateObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugFunctionObject::CreateObject](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfunctionobject-createobject).  
  
Bir oluşturucu kullanılarak bir nesne oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT CreateObject(   
   IDebugFunctionObject* pConstructor,  
   DWORD                 dwArgs,  
   IDebugObject*         pArgs[],  
   IDebugObject**        ppObject  
);  
```  
  
```csharp  
int CreateObject(  
   IDebugFunctionObject pConstructor,   
   uint                 dwArgs,   
   IDebugObject[]       pArgs,   
   out IDebugObject     ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pConstructor`  
 [in] Bir [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) Oluşturucusu oluşturulacak nesne, temsil eden nesne.  
  
 `dwArgs`  
 [in] Parametre sayısı `pArg` dizisi. Oluşturucuya geçirilen parametrelerin sayısını temsil eder.  
  
 `pArg`  
 [in] Bir dizi [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) oluşturucuya geçirilen parametreleri temsil eden nesneleri.  
  
 `ppObject`  
 [out] Döndürür bir `IDebugObject` temsil eden yeni oluşturulan nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir sınıf (veya bir oluşturucu gerektiren başka bir karmaşık tür) örneğini temsil eden bir nesne oluşturmak için bu yöntemi çağıran bir parametresi tarafından temsil edilen işlevi için diğer bir deyişle [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) arabirimi.  
  
 Nesne parametresi bir oluşturucu gerektirmiyorsa, çağrı [CreateObjectNoConstructor](../../../extensibility/debugger/reference/idebugfunctionobject-createobjectnoconstructor.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)   
 [CreateObjectNoConstructor](../../../extensibility/debugger/reference/idebugfunctionobject-createobjectnoconstructor.md)

