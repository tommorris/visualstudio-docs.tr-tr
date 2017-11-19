---
title: IDebugPointerObject::Dereference | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPointerObject::Dereference
helpviewer_keywords: IDebugPointerObject::Dereference method
ms.assetid: 196ec2cc-8569-4780-b217-23b24e7f50ca
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 928a49daf8c4bc2eedbe834a09293fcc767fd2bd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugpointerobjectdereference"></a>IDebugPointerObject::Dereference
İşaret nesnesini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT DeReference(   
   DWORD          dwIndex,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int Dereference(  
   uint             dwIndex,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwIndex`  
 [in] İşaret nesne başına basit bayt uzaklığı.  
  
 `ppObject`  
 [out] Döndürür bir [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) nesnesini temsil eden işaret artı uzaklığı, varsa nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür. Bu nesneyi başka bir nesneye işaret etmiyorsa E_FAIL döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 İşaret nesnesi, basit bir tür ya da bir sınıf veya yapı gibi daha karmaşık bir türü olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)