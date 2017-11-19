---
title: "İfade değerlendirme uyarlamasını örnek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- expression evaluators
- debugging [Debugging SDK], expression evaluators
- expression evaluation, examples
ms.assetid: 2a5f04b8-6c65-4232-bddd-9093653a22c4
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2cae1e8d697ba8079b29fa2188f0fb2f8b9a40e6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="sample-implementation-of-expression-evaluation"></a>İfade değerlendirme için örnek uygulama
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 İçin bir **izleme** penceresi ifade, Visual Studio çağrıları [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) üretmek için bir [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) nesnesi. `IDebugExpressionContext2::ParseText`bir ifade değerlendiricisi (EE) ve çağrıları başlatır [ayrıştırma](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) elde etmek için bir [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) nesnesi.  
  
 Bu uygulaması, `IDebugExpressionEvaluator::Parse` aşağıdaki görevleri gerçekleştirir:  
  
1.  [Yalnızca C++] Hataları aramak için ifade ayrıştırır.  
  
2.  Bir sınıf oluşturur (adlı `CParsedExpression` Bu örnekte) uygulayan `IDebugParsedExpression` arabirim ve sınıfında ayrıştırılması için ifadeyi depolar.  
  
3.  Döndürür `IDebugParsedExpression` alanından arabirim `CParsedExpression` nesnesi.  
  
> [!NOTE]
>  Örnekler ve MyCEE örnek, ifade değerlendiricisi ayrıştırma değerlendirme sürümünden ayrı değil.  
  
## <a name="managed-code"></a>Yönetilen kod  
 Bu bir uygulamasıdır `IDebugExpressionEvaluator::Parse` yönetilen kod. Yöntemi bu sürümü için ayrıştırma erteler Not [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) ayrıştırma kodunu da aynı anda değerlendirirken (bkz [Gözcü ifadesi değerlendirme](../../extensibility/debugger/evaluating-a-watch-expression.md)).  
  
```csharp  
namespace EEMC  
{  
    public class CParsedExpression : IDebugParsedExpression  
    {  
        public HRESULT Parse(  
                string                 expression,   
                uint                   parseFlags,  
                uint                   radix,  
            out string                 errorMessage,   
            out uint                   errorPosition,   
            out IDebugParsedExpression parsedExpression)  
        {   
            errorMessage = "";  
            errorPosition = 0;  
  
            parsedExpression =  
                new CParsedExpression(parseFlags, radix, expression);  
            return COM.S_OK;  
        }  
    }  
}  
```  
  
## <a name="unmanaged-code"></a>Yönetilmeyen Kod  
 Bu bir uygulamasıdır `IDebugExpressionEvaluator::Parse` yönetilmeyen kodunda. Yardımcı işlevi bu yöntemi çağırır `Parse`, hataları denetleyin ve ifade çözümlenemedi, ancak bu yöntem sonuç değeri yok sayar. Resmi değerlendirme için ertelenmiş [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) burada ifade ayrıştırılır ifadesine hesaplanmadan sırada (bkz [Gözcü ifadesi değerlendirme](../../extensibility/debugger/evaluating-a-watch-expression.md)).  
  
```cpp  
STDMETHODIMP CExpressionEvaluator::Parse(  
        in    LPCOLESTR                 pszExpression,  
        in    PARSEFLAGS                flags,  
        in    UINT                      radix,  
        out   BSTR                     *pbstrErrorMessages,  
        inout UINT                     *perrorCount,  
        out   IDebugParsedExpression  **ppparsedExpression  
    )  
{  
    if (pbstrErrorMessages == NULL)  
        return E_INVALIDARG;  
    else  
        *pbstrErrormessages = 0;  
  
    if (pparsedExpression == NULL)  
        return E_INVALIDARG;  
    else  
        *pparsedExpression = 0;  
  
    if (perrorCount == NULL)  
        return E_INVALIDARG;  
  
    HRESULT hr;  
    // Look for errors in the expression but ignore results  
    hr = ::Parse( pszExpression, pbstrErrorMessages );  
    if (hr != S_OK)  
        return hr;  
  
    CParsedExpression* pparsedExpr = new CParsedExpression( radix, flags, pszExpression );  
    if (!pparsedExpr)  
        return E_OUTOFMEMORY;  
  
    hr = pparsedExpr->QueryInterface( IID_IDebugParsedExpression,  
                                      reinterpret_cast<void**>(ppparsedExpression) );  
    pparsedExpr->Release();  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gözcü penceresi ifade değerlendirme](../../extensibility/debugger/evaluating-a-watch-window-expression.md)   
 [Gözcü ifadesi değerlendirme](../../extensibility/debugger/evaluating-a-watch-expression.md)