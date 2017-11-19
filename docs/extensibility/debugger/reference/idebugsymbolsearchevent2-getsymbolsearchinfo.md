---
title: IDebugSymbolSearchEvent2::GetSymbolSearchInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugSymbolSearchEvent2::GetSymbolSearchInfo
helpviewer_keywords: IDebugSymbolSearchEvent2::GetSymbolSearchInfo
ms.assetid: ae9eb72b-f2aa-43b8-87ca-da19d2e78d17
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bdf3b80a49641a13d9c17673376d70cfdee103cc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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