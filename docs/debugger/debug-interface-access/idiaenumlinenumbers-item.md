---
title: Idiaenumlinenumbers::Item | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumLineNumbers::Item method
ms.assetid: 08efbeaf-22f7-49e9-96a8-bb906dfe4fd8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0a00929311c1e8ccaa50d03543f072696bd2bf7f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaenumlinenumbersitem"></a>IDiaEnumLineNumbers::Item
Bir satır sayısı bir dizin yoluyla alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT Item (   
   DWORD            index,  
   IDiaLineNumber** lineNumber  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 dizin  
 [in] Dizin [Idialinenumber](../../debugger/debug-interface-access/idialinenumber.md) alınacak nesne. Aralıktaki 0 dizinidir `count`-1, burada `count` tarafından döndürülen [Idiaenumlinenumbers::get_Count](../../debugger/debug-interface-access/idiaenumlinenumbers-get-count.md) yöntemi.  
  
 lineNumber  
 [out] Döndürür bir [Idialinenumber](../../debugger/debug-interface-access/idialinenumber.md) istediğiniz satır numarasını temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumlinenumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)