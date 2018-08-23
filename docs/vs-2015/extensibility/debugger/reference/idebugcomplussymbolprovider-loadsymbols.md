---
title: IDebugComPlusSymbolProvider::LoadSymbols | Microsoft Docs
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
- LoadSymbols
- IDebugComPlusSymbolProvider::LoadSymbols
ms.assetid: 3499680d-0b9a-4f20-8432-c89a41b29b87
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 345549eb56390aec074e0299c0c9ae8d48dcd8f9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691852"
---
# <a name="idebugcomplussymbolproviderloadsymbols"></a>IDebugComPlusSymbolProvider::LoadSymbols
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugComPlusSymbolProvider::LoadSymbols](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcomplussymbolprovider-loadsymbols).  
  
Bellek belirtilen hata ayıklama sembolleri yükler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT LoadSymbols(  
   ULONG32   ulAppDomainID,  
   GUID      guidModule,  
   ULONGLONG baseAddress,  
   IUnknown* pUnkMetadataImport,  
   BSTR      bstrModuleName,  
   BSTR      bstrSymSearchPath  
);  
```  
  
```csharp  
int LoadSymbols(  
   uint   ulAppDomainID,  
   Guid   guidModule,  
   ulong  baseAddress,  
   object pUnkMetadataImport,  
   string bstrModuleName,  
   string bstrSymSearchPath  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ulAppDomainID`  
 [in] Uygulama etki alanı tanımlayıcısı.  
  
 `guidModule`  
 [in] Mondule benzersiz tanımlayıcısı.  
  
 `baseAddress`  
 [in] Temel bir bellek adresi.  
  
 `pUnkMetadataImport`  
 [in] Sembol meta veriler içeren nesne.  
  
 `bstrModuleName`  
 [in] Modülün adı.  
  
 `bstrSymSearchPath`  
 [in] Sembol dosyası için arama yolu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek için bu yöntemi uygulaması gösterilmiştir bir **CDebugSymbolProvider** gösteren nesne [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md) arabirimi.  
  
```cpp#  
HRESULT CDebugSymbolProvider::LoadSymbols(  
    ULONG32 ulAppDomainID,  
    GUID guidModule,  
    ULONGLONG baseOffset,  
    IUnknown* _pMetadata,  
    BSTR bstrModule,  
    BSTR bstrSearchPath)  
{  
    return LoadSymbolsWithCorModule(ulAppDomainID, guidModule, baseOffset, _pMetadata, NULL, bstrModule, bstrSearchPath);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)

