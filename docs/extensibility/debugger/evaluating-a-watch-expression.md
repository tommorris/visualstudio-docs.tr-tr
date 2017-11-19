---
title: "Gözcü ifadesi değerlendirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- expression evaluation, watch expressions
- watch expressions
ms.assetid: 8317cd52-6fea-4e8f-a739-774dc06bd44b
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0dfc63e378766fa6b50e52788d7117d767613bec
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="evaluating-a-watch-expression"></a>Gözcü ifadesi değerlendirme
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Visual Studio Gözcü ifadesi değerini görüntülemek hazır olduğunda, çağıran [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) sırayla çağıran [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md). Bu üreten bir [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) ifade türü ve değeri içeren nesne.  
  
 Bu uygulanmasını `IDebugParsedExpression::EvaluateSync`, ifade ayrıştırılır ve aynı anda değerlendirilir. Bu uygulama, aşağıdaki görevleri gerçekleştirir:  
  
1.  Ayrıştırır ve değer ve türünü içeren genel bir nesne oluşturmak için ifadeyi hesaplar. C# ' ta bu olarak temsil edilen bir `object` C++'da bu olarak temsil edilir sırada bir `VARIANT`.  
  
2.  Bir sınıf oluşturur (adlı `CValueProperty` Bu örnekte) uygulayan `IDebugProperty2` arabirim ve döndürülecek değer sınıfında depolar.  
  
3.  Döndürür `IDebugProperty2` alanından arabirim `CValueProperty` nesnesi.  
  
## <a name="managed-code"></a>Yönetilen kod  
 Bu bir uygulamasıdır `IDebugParsedExpression::EvaluateSync` yönetilen kod. Yardımcı yöntemi `Tokenize` ayrıştırma ağacı ifadesine ayrıştırır. Yardımcı işlevini `EvalToken` belirteci bir değerine dönüştürür. Yardımcı işlevini `FindTerm` yinelemeli olarak erişir ayrıştırma ağacı çağırma `EvalToken` bir değeri temsil eden ve herhangi bir işlem (ekleme veya çıkarma) ifade uygulayarak her düğüm için.  
  
```csharp  
namespace EEMC  
{  
    public class CParsedExpression : IDebugParsedExpression  
    {  
        public HRESULT EvaluateSync(  
            uint evalFlags,  
            uint timeout,  
            IDebugSymbolProvider provider,  
            IDebugAddress address,  
            IDebugBinder binder,  
            string resultType,  
            out IDebugProperty2 result)  
        {  
            HRESULT retval = COM.S_OK;  
            this.evalFlags = evalFlags;  
            this.timeout = timeout;  
            this.provider = provider;  
            this.address = address;  
            this.binder = binder;  
            this.resultType = resultType;  
  
            try  
            {  
                IDebugField field = null;  
                // Tokenize, then parse.  
                tokens = Tokenize(expression);  
                result = new CValueProperty(  
                             expression,  
                             (int) FindTerm(EvalToken(tokens[0], out field),1),  
                             field,  
                             binder);  
            }  
            catch (ParseException)  
            {  
                result = new CValueProperty(expression, "Huh?");  
                retval = COM.E_INVALIDARG;  
            }  
            return retval;  
        }  
    }  
}  
```  
  
## <a name="unmanaged-code"></a>Yönetilmeyen Kod  
 Bu bir uygulamasıdır `IDebugParsedExpression::EvaluateSync` yönetilmeyen kodunda. Yardımcı işlevini `Evaluate` ayrıştırır ve döndürme ifadeyi hesaplar bir `VARIANT` sonuç değeri tutan. Yardımcı işlevini `VariantValueToProperty` paketleri `VARIANT` içine bir `CValueProperty` nesnesi.  
  
```  
[C++]  
STDMETHODIMP CParsedExpression::EvaluateSync(   
    in  DWORD                 evalFlags,  
    in  DWORD                 dwTimeout,  
    in  IDebugSymbolProvider* pprovider,  
    in  IDebugAddress*        paddress,  
    in  IDebugBinder*         pbinder,  
    in  BSTR                  bstrResultType,  
    out IDebugProperty2**     ppproperty )  
{  
    // dwTimeout parameter is ignored in this implementation.  
    if (pprovider == NULL)  
        return E_INVALIDARG;  
  
    if (paddress == NULL)  
        return E_INVALIDARG;  
  
    if (pbinder == NULL)  
        return E_INVALIDARG;  
  
    if (ppproperty == NULL)  
        return E_INVALIDARG;  
    else  
        *ppproperty = 0;  
  
    HRESULT hr;  
    VARIANT value;  
    BSTR    bstrErrorMessage = NULL;  
    hr = ::Evaluate( pprovider,  
                     paddress,  
                     pbinder,  
                     m_expr,  
                     &bstrErrorMessage,  
                     &value );  
    if (hr != S_OK)  
    {  
        if (bstrErrorMessage == NULL)  
            return hr;  
  
        //we can display better messages ourselves.  
        HRESULT hrLocal = S_OK;  
        VARIANT varType;  
        VARIANT varErrorMessage;  
  
        VariantInit( &varType );  
        VariantInit( &varErrorMessage );  
        varErrorMessage.vt      = VT_BSTR;  
        varErrorMessage.bstrVal = bstrErrorMessage;  
  
        CValueProperty* valueProperty = new CValueProperty();  
        if (valueProperty != NULL)  
        {  
            hrLocal = valueProperty->Init(m_expr, varType, varErrorMessage);  
            if (SUCCEEDED(hrLocal))   
            {  
                hrLocal = valueProperty->QueryInterface( IID_IDebugProperty2,  
                        reinterpret_cast<void**>(ppproperty) );  
            }  
        }  
  
        VariantClear(&varType);  
        VariantClear(&varErrorMessage); //frees BSTR  
        if (!valueProperty)  
            return hr;  
        valueProperty->Release();  
        if (FAILED(hrLocal))  
            return hr;  
    }  
    else  
    {  
        if (bstrErrorMessage != NULL)  
            SysFreeString(bstrErrorMessage);  
  
        hr = VariantValueToProperty( pprovider,  
                                     paddress,  
                                     pbinder,  
                                     m_radix,  
                                     m_expr,  
                                     value,  
                                     ppproperty );  
        VariantClear(&value);  
        if (FAILED(hr))  
            return hr;  
    }  
  
    return S_OK;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gözcü penceresi ifade değerlendirme](../../extensibility/debugger/evaluating-a-watch-window-expression.md)   
 [İfade değerlendirme için örnek uygulama](../../extensibility/debugger/sample-implementation-of-expression-evaluation.md)