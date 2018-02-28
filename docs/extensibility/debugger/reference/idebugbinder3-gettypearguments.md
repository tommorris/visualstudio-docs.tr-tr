---
title: IDebugBinder3::GetTypeArguments | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugBinder3::GetTypeArguments
helpviewer_keywords:
- IDebugBinder3::GetTypeArguments method
ms.assetid: fa0c37a7-327f-463e-9a9d-bb3f534584cb
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9d04bc40b559b785a659945ac75838303e59e658
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugbinder3gettypearguments"></a>IDebugBinder3::GetTypeArguments
Bu yöntem bağımsız değişken türleri Bu nesneyle ilişkili bir listesini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetTypeArguments(  
   UINT          skip,  
   UINT          count,  
   IDebugField** ppFields,  
   UINT*         pFetched  
);  
```  
  
```csharp  
int GetTypeArguments(  
   uint          skip,  
   uint          count,  
   IDebugField[] ppFields,  
   out uint      pFetched  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `skip`  
 [in] Bağımsız değişken türleri almadan önce atlamak için alanları sayısı.  
  
 `count`  
 [in] Döndürülecek bağımsız değişken alan sayısını (aynı zamanda boyutunu belirtir `ppFields` array).  
  
 `ppFields`  
 [içinde out] Bu yöntem getirisi doldurulur alanları dizisi.  
  
 `pFetched`  
 [out] \(isteğe bağlı) Bağımsız değişken sayısı gerçekte döndürülen alanları yazın.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bağımsız değişken türleri sayısı ile önceden alınabilir [GetTypeArgumentCount](../../../extensibility/debugger/reference/idebugbinder3-gettypeargumentcount.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)   
 [GetTypeArgumentCount](../../../extensibility/debugger/reference/idebugbinder3-gettypeargumentcount.md)