---
title: IDebugSettingsCallback2 | Microsoft Docs
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
- IDebugSettingsCallback2 interface
ms.assetid: 7e525d0b-7d7a-4d1c-8b78-e1398fa922f2
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 184cab04a4eaca2bf444bd31d6c97a3e6f0f7685
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629771"
---
# <a name="idebugsettingscallback2"></a>IDebugSettingsCallback2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugSettingsCallback2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugsettingscallback2).  
  
Hata ayıklama altyapıları Ölçüm ayarlarını okumak üzere etkinleştirir uzaktan.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugSettingsCallback2D : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Bu arabirim oturum hata ayıklama Yöneticisi olay geri çağırma tarafından uygulanan ve hata ayıklama motoru tarafından kullanılan. Bu da yerel olarak Dbgmetric [d] .lib yerine kullanılabilir.  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugSettingsCallback2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[EnumEEs](../../../extensibility/debugger/reference/idebugsettingscallback2-enumees.md)|Dil ve satıcı tanımlayıcıları verilen kullanılabilir ifade değerlendiricilerini numaralandırır.|  
|[GetEELocalObject](../../../extensibility/debugger/reference/idebugsettingscallback2-geteelocalobject.md)|Ölçüm verilen bir ifade değerlendirici yerel bir nesne alır.|  
|[GetEEMetricDword](../../../extensibility/debugger/reference/idebugsettingscallback2-geteemetricdword.md)|İfade değerlendirici belirtilen ölçüm için karşılık gelen bir değer alır.|  
|[GetEEMetricFile](../../../extensibility/debugger/reference/idebugsettingscallback2-geteemetricfile.md)|Ad veya ölçüm verilen ifade değerlendirici ölçüm dosya alır.|  
|[GetEEMetricGuid](../../../extensibility/debugger/reference/idebugsettingscallback2-geteemetricguid.md)|Bir ifade değerlendirici ölçüm adı verilen benzersiz tanımlayıcısını alır.|  
|[GetEEMetricString](../../../extensibility/debugger/reference/idebugsettingscallback2-geteemetricstring.md)|Bir ifade değerlendirici ölçüm adı verilen değer dizesi alır.|  
|[GetMetricDword](../../../extensibility/debugger/reference/idebugsettingscallback2-getmetricdword.md)|Adı verilen bir ölçüm değerini alır.|  
|[GetMetricGuid](../../../extensibility/debugger/reference/idebugsettingscallback2-getmetricguid.md)|Bir ölçüm adı verilen benzersiz tanımlayıcısını alır.|  
|[GetMetricString](../../../extensibility/debugger/reference/idebugsettingscallback2-getmetricstring.md)|Ölçüm adı verilen değer dizesi alır.|  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, alan bir işlev gösterir. bir **IDebugSettingsCallback2** bir parametre olarak nesne.  
  
```cpp#  
HRESULT GetDebugSettingsCallback (IDebugSettingsCallback2 **ppCallback)  
{  
    HRESULT hRes = E_FAIL;  
  
    if ( ppCallback )  
   {  
        if ( EVAL(m_pdec) )  
            hRes = m_pdec->QueryInterface(IID_IDebugSettingsCallback2, (void **)ppCallback);  
        else  
            hRes = E_FAIL;  
    }  
    else  
        hRes = E_INVALIDARG;  
  
    return ( hRes );  
}  
```

