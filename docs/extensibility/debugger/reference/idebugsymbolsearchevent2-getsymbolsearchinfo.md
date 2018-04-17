---
title: IDebugSymbolSearchEvent2::GetSymbolSearchInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugSymbolSearchEvent2::GetSymbolSearchInfo
helpviewer_keywords:
- IDebugSymbolSearchEvent2::GetSymbolSearchInfo
ms.assetid: ae9eb72b-f2aa-43b8-87ca-da19d2e78d17
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 518429149ad1d997b860e486f3db4e519ef42cae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugsymbolsearchevent2getsymbolsearchinfo"></a>IDebugSymbolSearchEvent2::GetSymbolSearchInfo
Simge yükleme işlemiyle ilgili sonuçları almak için bir olay işleyicisi tarafından çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
   IDebugModule3**    pModule,  
   BSTR*              pbstrDebugMessage,  
   MODULE_INFO_FLAGS* pdwModuleInfoFlags  
);  
```  
  
```csharp  
int GetSymbolSearchInfo(  
   IDebugModule3              pModule,   
   ref string                 pbstrDebugMessage,   
   out enum_MODULE_INFO_FLAGS pdwModuleInfoFlags  
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pModule`  
 [out] Kendisi için simgeler yüklenen modülü temsil eden bir IDebugModule3 nesnesi.  
  
 `pbstrDebugMessage`  
 [içinde out] Modülden herhangi bir hata iletisi içeren bir dize döndürür. Herhangi bir hata varsa, bu dize modülün adı yalnızca içerir ancak hiçbir zaman boştur.  
  
> [!NOTE]
>  [C++] `pbstrDebugMessage` olamaz `NULL` ve ile boşaltılması `SysFreeString`.  
  
 `pdwModuleInfoFlags`  
 [out] Bayraklarını bileşimini [MODULE_INFO_FLAGS](../../../extensibility/debugger/reference/module-info-flags.md) semboller yüklenmiş olup olmadığını belirten numaralandırma.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Ne zaman bir işleyici alır [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md) modülü için hata ayıklama simgeleri yüklemek için bir girişimde sonra olay işleyicisi, yükleme sonuçlarını belirlemek için bu yöntem çağırabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)   
 [MODULE_INFO_FLAGS](../../../extensibility/debugger/reference/module-info-flags.md)   
 [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)