---
title: IDebugExpressionContext2::ParseText | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugExpressionContext2::ParseText
helpviewer_keywords:
- IDebugExpressionContext2::ParseText
ms.assetid: f58575db-f926-4ac8-83ff-7b3b86ab61e2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e95a8a76e7315f8963ea415f88bd9615f3b123a4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31112815"
---
# <a name="idebugexpressioncontext2parsetext"></a>IDebugExpressionContext2::ParseText
Sonraki değerlendirme için metin biçiminde bir ifade ayrıştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT ParseText(   
   LPCOLESTR           pszCode,  
   PARSEFLAGS          dwFlags,  
   UINT                nRadix,  
   IDebugExpression2** ppExpr,  
   BSTR*               pbstrError,  
   UINT*               pichError  
);  
```  
  
```csharp  
int ParseText(   
   string                pszCode,  
   enum_PARSEFLAGS       dwFlags,  
   uint                  nRadix,  
   out IDebugExpression2 ppExpr,  
   out string            pbstrError,  
   out uint              pichError  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pszCode`  
 [in] Ayrıştırılacak ifade.  
  
 `dwFlags`  
 [in] Bayraklarını bileşimini [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md) ayrıştırma denetimleri numaralandırması.  
  
 `nRadix`  
 [in] Sayısal bilgileri Ayrıştırmada kullanılacak taban `pszCode`.  
  
 `ppExpr`  
 [out] Döndürür [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md) bağlama ve değerlendirme için hazır ayrıştırılmış ifadeyi temsil eden nesne.  
  
 `pbstrError`  
 [out] İfade bir hata varsa hata iletisi döndürür.  
  
 `pichError`  
 [out] Hata karakter dizinini döndürür `pszCode` ifadesi bir hata içeriyorsa.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem çağrıldığında, hata ayıklama altyapısı (DE) ifade ayrıştırabilir ve doğruluğu doğrulayın. `pbstrError` Ve `pichError` parametreleri doldurulmuş ifade geçersizse.  
  
 İfade, yalnızca Ayrıştırılan değerlendirilmez olduğunu unutmayın. Sonraki çağrı [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) veya [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) yöntemleri ayrıştırılmış ifadeyi değerlendirir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte basit bir için bu yöntemi uygulaması gösterilmektedir `CEnvBlock` gösteren nesne [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md) arabirimi. Bu örnek bir ortam değişkeni adı olarak ayrıştırılacak ifade olarak değerlendirir ve bu değişkeninden değeri alır.  
  
```cpp  
HRESULT CEnvBlock::ParseText(  
   LPCOLESTR           pszCode,  
   PARSEFLAGS          dwFlags,  
   UINT                nRadix,  
   IDebugExpression2 **ppExpr,  
   BSTR               *pbstrError,  
   UINT               *pichError)  
{  
   HRESULT hr = E_OUTOFMEMORY;    
   // Create an integer variable with a value equal to one plus    
   // twice the length of the passed expression to be parsed.    
   int iAnsiLen      = 2 * (wcslen(pszCode)) + 1;    
   // Allocate a character string of the same length.    
   char *pszAnsiCode = (char *) malloc(iAnsiLen);    
  
   // Check for successful memory allocation.    
   if (pszAnsiCode) {    
      // Map the wide-character pszCode string to the new pszAnsiCode character string.    
      WideCharToMultiByte(CP_ACP, 0, pszCode, -1, pszAnsiCode, iAnsiLen, NULL, NULL);    
      // Check to see if the app can succesfully get the environment variable.    
      if (GetEnv(pszAnsiCode)) {    
  
         // Create and initialize a CExpression object.    
         CComObject<CExpression> *pExpr;    
         CComObject<CExpression>::CreateInstance(&pExpr);    
            pExpr->Init(pszAnsiCode, this, NULL);    
  
         // Assign the pointer to the new object to the passed argument  
         // and AddRef the object.    
         *ppExpr = pExpr;    
         (*ppExpr)->AddRef();    
         hr = S_OK;    
      // If the program cannot succesfully get the environment variable.    
      } else {    
         // Set the errror message and return E_FAIL.    
         *pbstrError = SysAllocString(L"No such environment variable.");    
         hr = E_FAIL;    
      }    
      // Free the local character string.    
      free(pszAnsiCode);    
   }    
   return hr;    
}    
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md)   
 [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md)   
 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)   
 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)