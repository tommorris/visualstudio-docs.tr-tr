---
title: Idiaenumsymbolsbyaddr::symbolbyaddr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSymbolsByAddr::symbolByAddr method
ms.assetid: 0b6f5a68-8402-4f29-8219-20576fda8166
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 159c6fcc65734255f5303ee267a1368078f7af10
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaenumsymbolsbyaddrsymbolbyaddr"></a>IDiaEnumSymbolsByAddr::symbolByAddr
Numaralayıcı görüntü bölüm numarası ve uzaklık aramasından gerçekleştirerek yerleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT symbolByAddr (   
   DWORD**      isect,  
   DWORD**      offsect,  
   IDiaSymbol** ppsymbol  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 isect  
 [in] Görüntü bölüm numarası.  
  
 offsect  
 [in] Bölümünde uzaklık.  
  
 ppsymbol  
 [out] Döndürür bir [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md) bulunan simgeyi temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`. Döndürür `S_FALSE` simgenin bulunamazsa. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumsymbolsbyaddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)