---
title: Idiaenumınjectedsources::Item | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumInjectedSources::Item method
ms.assetid: 14846955-7270-451d-91d2-9cb34bb65187
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7fb753605a85dedefac5fc2cd33f4baf158b128b
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaenuminjectedsourcesitem"></a>IDiaEnumInjectedSources::Item
Eklenen bir kaynak dizin yoluyla alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT Item (   
   DWORD                index,  
   IDiaInjectedSource** injectedSource  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 dizin  
 [in] Dizin [Idiaınjectedsource](../../debugger/debug-interface-access/idiainjectedsource.md) alınacak nesne. Dizin 0 için aralığı `count`-1, burada `count` tarafından döndürülen [Idiaenumınjectedsources::get_Count](../../debugger/debug-interface-access/idiaenuminjectedsources-get-count.md) yöntemi.  
  
 injectedSource  
 [out] Döndürür bir [Idiaınjectedsource](../../debugger/debug-interface-access/idiainjectedsource.md) eklenen kaynak temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumınjectedsources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)   
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)