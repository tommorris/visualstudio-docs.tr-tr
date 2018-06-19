---
title: IDebugExpressionEvaluator::Parse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugExpressionEvaluator::Parse
helpviewer_keywords:
- IDebugExpressionEvaluator::Parse method
ms.assetid: e6e31b3a-63a7-4293-bcda-267eb78dffb6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2a10a65564682b5c82350eb5c22af3f217a3a993
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31110809"
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