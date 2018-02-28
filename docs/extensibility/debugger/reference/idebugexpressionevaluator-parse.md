---
title: IDebugExpressionEvaluator::Parse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugExpressionEvaluator::Parse
helpviewer_keywords:
- IDebugExpressionEvaluator::Parse method
ms.assetid: e6e31b3a-63a7-4293-bcda-267eb78dffb6
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e64d7419973f0505a2413d7ea56be12a31d01a1c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugexpressionevaluatorparse"></a>IDebugExpressionEvaluator::Parse
Bu yöntem için ayrıştırılmış bir ifade bir ifade dizesini sayıya dönüştürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Parse(   
   LPCOLESTR                upstrExpression,  
   PARSEFLAGS               dwFlags,  
   UINT                     nRadix,  
   BSTR*                    pbstrError,  
   UINT*                    pichError,  
   IDebugParsedExpression** ppParsedExpression  
);  
```  
  
```csharp  
int Parse(  
   string                     upstrExpression,   
   enum_PARSEFLAGS            dwFlags,   
   uint                       nRadix,   
   out string                 pbstrError,   
   out uint                   pichError,   
   out IDebugParsedExpression ppParsedExpression  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `upstrExpression`  
 [in] Ayrıştırılacak ifade dizesi.  
  
 `dwFlags`  
 [in] Bir koleksiyonu [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md) ifade nasıl ayrıştırılması belirleme sabitleri.  
  
 `nRadix`  
 [in] Tüm sayısal bilgilerini yorumlamak için kullanılacak sayı tabanını.  
  
 `pbstrError`  
 [out] Hata okunabilir metin olarak döndürür.  
  
 `pichError`  
 [out] Hata başlangıç karakteri konumunu ifade dizesini döndürür.  
  
 `ppParsedExpression`  
 [out] Ayrıştırılmış ifadesinde döndüren bir [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md) nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, ayrıştırılmış bir ifade, gerçek bir değer oluşturur. Ayrıştırılmış ifadesi başka bir deyişle, değerine dönüştürülüp değerlendirilmesi hazırdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)   
 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)   
 [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md)