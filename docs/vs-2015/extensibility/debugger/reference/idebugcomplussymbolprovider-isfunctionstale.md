---
title: IDebugComPlusSymbolProvider::IsFunctionStale | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugComPlusSymbolProvider::IsFunctionStale
ms.assetid: dcffc090-4ed8-47b2-ba51-bce1a6b6428d
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 694c751af64362cc1e35baca170bfcdae47350dd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694764"
---
# <a name="idebugcomplussymbolproviderisfunctionstale"></a>IDebugComPlusSymbolProvider::IsFunctionStale
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugComPlusSymbolProvider::IsFunctionStale](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcomplussymbolprovider-isfunctionstale).  
  
Belirtilen hata ayıklama adresten işlevi eski olarak kabul edileceğini belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT IsFunctionStale(  
   IDebugAddress* pAddress  
);  
```  
  
```csharp  
int IsFunctionStale(  
   IDebugAddress pAddress  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pAddress`  
 [in] Tarafından temsil edilen hata ayıklama adresi bir [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) arabirimi. Bu adresi bir METHOD_ADDRESS olmalıdır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlev eski kabul ediliyorsa döndürür `S_OK`. İşlev eski değilse döndürür `S_FALSE`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek için bu yöntemi uygulaması gösterilmiştir bir **CDebugSymbolProvider** gösteren nesne [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md) arabirimi.  
  
```cpp#  
HRESULT CDebugSymbolProvider::IsFunctionStale(  
    IDebugAddress* pAddress  
)  
{  
    HRESULT hr = S_OK;  
    CDEBUG_ADDRESS address;  
    CComPtr<CModule> pModule;  
  
    ASSERT(IsValidObjectPtr(this, CDebugSymbolProvider));  
    ASSERT(IsValidInterfacePtr(pAddress, IDebugAddress));  
  
    METHOD_ENTRY( CDebugSymbolProvider::IsFunctionStale );  
  
    IfFalseGo( pAddress, S_FALSE );  
    IfFailGo( pAddress->GetAddress( &address ) );  
  
    ASSERT(address.addr.dwKind == ADDRESS_KIND_METADATA_METHOD);  
    IfFalseGo( address.addr.dwKind == ADDRESS_KIND_METADATA_METHOD, S_FALSE );  
  
    IfFailGo( GetModule( address.GetModule(), &pModule) );  
  
    if (!pModule->IsFunctionStale( address.addr.addr.addrMethod.tokMethod,  
                                   address.addr.addr.addrMethod.dwVersion ))  
    {  
  
        // S_FALSE indicates the function is not stale  
  
        hr = S_FALSE;  
    }  
  
Error:  
  
    METHOD_EXIT( CDebugSymbolProvider::IsFunctionStale, hr );  
  
    if (!SUCCEEDED(hr))  
    {  
        hr = S_FALSE;  
    }  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)

