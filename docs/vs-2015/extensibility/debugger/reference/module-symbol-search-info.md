---
title: MODULE_SYMBOL_SEARCH_INFO | Microsoft Docs
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
- MODULE_SYMBOL_SEARCH_INFO
helpviewer_keywords:
- MODULE_SYMBOL_SEARCH_INFO structure
ms.assetid: 432aff03-08a5-4c5a-b2d5-e212090fc70a
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 074e837a1c0449420d7042539fb4c8dfa0396fe6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686395"
---
# <a name="modulesymbolsearchinfo"></a>MODULE_SYMBOL_SEARCH_INFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [MODULE_SYMBOL_SEARCH_INFO](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/module-symbol-search-info).  
  
Arandığını sembol arama yolları hakkındaki durum bilgilerini içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
typedef struct _tagSYMBOL_SEARCH_INFO  
{  
   SYMBOL_SEARCH_INFO_FIELDS dwValidFields;  
   BSTR                      bstrVerboseSearchInfo;  
} MODULE_SYMBOL_SEARCH_INFO;  
```  
  
```csharp  
public struct MODULE_SYMBOL_SEARCH_INFO {  
   public uint   dwValidFields;  
   public string bstrVerboseSearchInfo;  
}  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwValidFields`  
 Bayraklarının bir birleşimi [SYMBOL_SEARCH_INFO_FIELDS](../../../extensibility/debugger/reference/symbol-search-info-fields.md) bu yapısı içinde açıklanan arama bilgi türünü belirten sabit listesi.  
  
 `bstrVerboseSearchInfo`  
 Arama yolu ve tek bir dize olarak birleştirilmiş sonuçlar.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı çağrısından döndürülen [GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md) yöntemi.  
  
 Varsa `bstrVerboseSearchInfo` alanı boş değil ve ardından arama yolları ve bu arama sonuçlarının bir listesini içerir. Listenin sonuca göre ve ardından üç nokta ("..."), ardından bir yol ile biçimlendirilir. Birden fazla yol sonuç çifti varsa, her bir çifti "\r\n" (satır başı-başı/satır besleme) çifti tarafından ayrılmış. Desen şöyle görünür:  
  
 \<yolu >... \<sonucu > \r\n\<yolu >... \<sonucu > \r\n\<yolu >... \<sonucu >  
  
 En son giriş \r\n dizisi yok unutmayın.  
  
 Olası bir işte `bstrVerboseSearchInfo` standart çıkış için gönderilen bir dize.  
  
 `c:\symbols\user32.pdb... File not found.`  
  
 `c:\winnt\symbols\user32.pdb... Version does not match.`  
  
 `\\symbols\symbols\user32.dll\0a8sd0ad8ad\user32.pdb... Symbols loaded.`  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimler](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md)

