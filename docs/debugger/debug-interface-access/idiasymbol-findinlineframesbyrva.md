---
title: IDiaSymbol::findInlineFramesByRVA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e7a6d9cb-2726-4ac7-9f38-415ad215bf9c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3e9b3778072ea3643bc672516ab16d318669ac85
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasymbolfindinlineframesbyrva"></a>IDiaSymbol::findInlineFramesByRVA
Tüm satır içi çerçeveler bir adresinde belirtilen göreli sanal (RVA) yinelemek bir istemci izin veren bir numaralandırmasını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT findInlineFramesByRVA (    DWORD             rva,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `rva`  
 [in] Adresini bir RVA belirtir.  
  
 `ppResult`  
 [out] Tutan bir `IDiaEnumSymbols` alınır çerçeveler listesini içeren nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)