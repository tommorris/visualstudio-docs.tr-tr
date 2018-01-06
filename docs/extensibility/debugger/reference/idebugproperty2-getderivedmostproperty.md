---
title: IDebugProperty2::GetDerivedMostProperty | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProperty2::GetDerivedMostProperty
helpviewer_keywords: IDebugProperty2::GetDerivedMostProperty
ms.assetid: cc86b461-62d1-4340-8209-c65037fd8b02
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4e9efd498485340b49dbd385a6a94fa6cf7fcedd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugproperty2getderivedmostproperty"></a>IDebugProperty2::GetDerivedMostProperty
Bir özelliğin türetilmiş çoğu özelliğini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetDerivedMostProperty (   
   IDebugProperty2** ppDerivedMost  
);  
```  
  
```csharp  
int GetDerivedMostProperty (   
   out IDebugProperty2 ppDerivedMost  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppDerivedMost`  
 [out] Döndürür bir [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) türetilmiş çoğu özelliği temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde hata kodunu döndürür. Döndürür `S_GETDERIVEDMOST_NO_DERIVED_MOST` almak için bir türetilmiş çoğu özellik ise.  
  
## <a name="remarks"></a>Açıklamalar  
 Örneğin, bu özellik uygulayan bir nesne tanımlarsa `ClassRoot` ancak aslında, örnekleme olduğu `ClassDerived` öğesinden türetilen `ClassRoot`, sonra da bu yöntemi döndürür bir [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) nesnesi açıklayan `ClassDerived` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)