---
title: GetMethodProperty uygulama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- GetMethodProperty method
- IDebugExpressionEvaluator2 property
ms.assetid: 6305874f-a2c4-4432-834c-07530ea84bff
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e3ed7207237a20e4dadc1284aca2d6b41a671353
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31102024"
---
# <a name="implementing-getmethodproperty"></a>GetMethodProperty uygulama
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Visual Studio hata ayıklama altyapısının (DE) çağırır [GetDebugProperty](../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md), sırayla çağıran [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) yığın çerçevesinde geçerli yöntemi hakkında bilgi edinmek için.  
  
 Bu uygulaması, `IDebugExpressionEvaluator::GetMethodProperty` aşağıdaki görevleri gerçekleştirir:  
  
1.  Çağrıları [GetContainerField](../../extensibility/debugger/reference/idebugsymbolprovider-getcontainerfield.md), içinde geçen [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md) nesnesi. Sembol sağlayıcısı (SP) döndüren bir [IDebugContainerField](../../extensibility/debugger/reference/idebugcontainerfield.md) belirtilen adresi içeriyor yöntemi temsil eden.  
  
2.  Edinir [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) gelen `IDebugContainerField`.  
  
3.  Bir sınıf oluşturur (adlı `CFieldProperty` Bu örnekte) uygulayan [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) arabirim ve içeren `IDebugMethodField` nesne SP'yi döndürdü  
  
4.  Döndürür `IDebugProperty2` alanından arabirim `CFieldProperty` nesnesi.  
  
## <a name="managed-code"></a>Yönetilen kod  
 Bu örnek uygulaması gösterir `IDebugExpressionEvaluator::GetMethodProperty` yönetilen kod.  
  
```csharp  
namespace EEMC  
{  
    [GuidAttribute("462D4A3D-B257-4AEE-97CD-5918C7531757")]  
    public class EEMCClass : IDebugExpressionEvaluator  
    {  
        public HRESULT GetMethodProperty(  
                IDebugSymbolProvider symbolProvider,  
                IDebugAddress        address,  
                IDebugBinder         binder,  
                int                  includeHiddenLocals,  
            out IDebugProperty2      property)   
        {  
            IDebugContainerField containerField = null;  
            IDebugMethodField methodField       = null;  
            property = null;  
  
            // Get the containing method field.  
            symbolProvider.GetContainerField(address, out containerField);  
            methodField = (IDebugMethodField) containerField;  
  
            // Return the property of method field.  
            property = new CFieldProperty(symbolProvider, address, binder, methodField);  
            return COM.S_OK;  
        }  
    }  
}  
```  
  
## <a name="unmanaged-code"></a>Yönetilmeyen Kod  
 Bu örnek uygulaması gösterir `IDebugExpressionEvaluator::GetMethodProperty` yönetilmeyen kodunda.  
  
```  
[CPP]  
STDMETHODIMP CExpressionEvaluator::GetMethodProperty(  
        in IDebugSymbolProvider *pprovider,  
        in IDebugAddress        *paddress,  
        in IDebugBinder         *pbinder,  
        in BOOL                  includeHiddenLocals,  
        out IDebugProperty2    **ppproperty  
    )  
{  
    if (pprovider == NULL)  
        return E_INVALIDARG;  
  
    if (ppproperty == NULL)  
        return E_INVALIDARG;  
    else  
        *ppproperty = 0;  
  
    HRESULT hr;  
    IDebugContainerField* pcontainer = NULL;  
  
    hr = pprovider->GetContainerField(paddress, &pcontainer);  
    if (FAILED(hr))  
        return hr;  
  
    IDebugMethodField*    pmethod    = NULL;  
    hr = pcontainer->QueryInterface( IID_IDebugMethodField,  
            reinterpret_cast<void**>(&pmethod));  
    pcontainer->Release();  
    if (FAILED(hr))  
        return hr;  
  
    CFieldProperty* pfieldProperty = new CFieldProperty( pprovider,  
                                                         paddress,  
                                                         pbinder,  
                                                         pmethod );  
    pmethod->Release();  
    if (!pfieldProperty)  
        return E_OUTOFMEMORY;  
  
    hr = pfieldProperty->Init();  
    if (FAILED(hr))  
    {  
        pfieldProperty->Release();  
        return hr;  
    }  
  
    hr = pfieldProperty->QueryInterface( IID_IDebugProperty2,  
            reinterpret_cast<void**>(ppproperty));  
    pfieldProperty->Release();  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Örnek Yerel Öğeler Uygulaması](../../extensibility/debugger/sample-implementation-of-locals.md)