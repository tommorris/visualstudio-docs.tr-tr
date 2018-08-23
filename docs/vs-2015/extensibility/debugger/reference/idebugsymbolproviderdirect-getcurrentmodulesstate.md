---
title: IDebugSymbolProviderDirect::GetCurrentModulesState | Microsoft Docs
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
- GetCurrentModulesState
- IDebugSymbolProviderDirect::GetCurrentModulesState
ms.assetid: a0c85318-5686-4eed-b213-21f2b9e681e6
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5b98bf45d868fb756cd2aa535de818aa1c2eeb9d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695754"
---
# <a name="idebugsymbolproviderdirectgetcurrentmodulesstate"></a>IDebugSymbolProviderDirect::GetCurrentModulesState
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugSymbolProviderDirect::GetCurrentModulesState](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugsymbolproviderdirect-getcurrentmodulesstate).  
  
Sembol sağlayıcısı üyesi olduğu simgesi grubu hakkındaki bilgileri alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetCurrentModulesState(  
    DWORD*          pState,  
    unsigned long * count  
);  
```  
  
```csharp  
int GetCurrentModulesState(  
    out uint pState,  
    out uint count  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pState`  
 [out] Sembol sağlayıcısı grubunun durumu.  
  
 `count`  
 [out] Gruptaki modül sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Her bir modül için eklendi veya sembol, gruptan durumu değiştirilir. Bu nedenle, bu yöntem bir sembol grubu değiştirilip değiştirilmediğini algılamak için kullanılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)

