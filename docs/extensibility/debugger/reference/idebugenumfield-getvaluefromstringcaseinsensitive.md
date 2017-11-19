---
title: IDebugEnumField::GetValueFromStringCaseInsensitive | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEnumField::GetValueFromStringCaseInsensitive
helpviewer_keywords: IDebugEnumField::GetValueFromStringCaseInsensitive method
ms.assetid: ef95b38e-d9b2-4fb5-a166-7c2e14641dc7
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8f1ff74931ac5433ff22330bc6f218315ccaf259
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugenumfieldgetvaluefromstringcaseinsensitive"></a>IDebugEnumField::GetValueFromStringCaseInsensitive
Bu yöntem duyarsız arama bir numaralandırma sabiti adı ile ilişkili değer döndürmek için kullanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetValueFromStringCaseInsensitive(  
   LPCOLESTR  pszValue,  
   ULONGLONG* pvalue  
);  
```  
  
```csharp  
int GetValueFromStringCaseInsensitive(  
   string    pszValue,   
   out ulong pValue  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pszValue`  
 [in] Değerin alınacağı adını belirten dize. C++ için bu bir geniş karakter dizesi olduğunu unutmayın.  
  
 `pValue`  
 [out] İlişkili sayısal değeri döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE`, ad numaralandırma veya bir hata kodu parçası değil.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, büyük/küçük harf duyarlıdır. Büyük küçük harfe duyarlı arama (örneğin, bir dilde burada adları büyük küçük harfe duyarlı C++ gibi) gerekiyorsa, kullanın [GetValueFromString](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstring.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)   
 [GetValueFromString](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstring.md)