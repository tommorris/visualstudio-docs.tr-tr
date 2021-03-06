---
title: IDebugModule2::ReloadSymbols_Deprecated | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugModule2::ReloadSymbols
helpviewer_keywords:
- IDebugModule2::ReloadSymbols method
ms.assetid: 0f9f0133-7d58-4cd9-a6ca-1141e095749d
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5a8c42ddcde84524819f2c8f828fa72c8617d423
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691846"
---
# <a name="idebugmodule2reloadsymbolsdeprecated"></a>IDebugModule2::ReloadSymbols_Deprecated
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugModule2::ReloadSymbols_Deprecated](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmodule2-reloadsymbols-deprecated).  
  
ARTIK KULLANILMIYOR. KULLANMAYIN. Bu modüle ilişkin simgeleri yeniden yükler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT ReloadSymbols(   
   LPCOLESTR pszUrlToSymbols,  
   BSTR*     pbstrDebugMessage  
);  
```  
  
```csharp  
int ReloadSymbols(   
   string     pszUrlToSymbols,  
   out string pbstrDebugMessage  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pszUrlToSymbols`  
 [in] Sembol deposu yolu.  
  
 `pbstrDebugMessage`  
 [out] Örneğin modül adı modüller penceresini sağındaki görüntülenen bir durum veya hata iletisi, bir bilgilendirme iletisi döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Hata ayıklama altyapısı her zaman döndürmelidir `E_FAIL`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem artık desteklenmiyor. Uygulama [LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md) yöntemi yerine.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md)

