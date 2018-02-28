---
title: IDiaSymbol::findChildrenExByVA | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::findChildrenExByVA
ms.assetid: 29080009-36e4-4697-acd7-50f2e3e1bf1b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 2d531bff72dbc8b5733c4a25ad243a8dae1d55b2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolfindchildrenexbyva"></a>IDiaSymbol::findChildrenExByVA
Belirtilen sanal adresinde geçerli öğenin alt öğelerine simgenin alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT findChildrenExByVA (   
   enum SymTagEnum   symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   DWORD             address,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `symtag`  
 [in] ' Da tanımlandığı gibi alınması için alt simge etiketleri belirtir [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md). Kümesine `SymTagNull` alınması tüm alt öğeleri için.  
  
 `name`  
 [in] Alınacak öğenin alt öğelerine adını belirtir. Kümesine `NULL` alınması tüm alt öğeleri için.  
  
 `compareFlags`  
 [in] Ad eşleştirme için uygulanacak karşılaştırma seçeneklerini belirtir. Gelen değerleri [NameSearchOptions numaralandırması](../../debugger/debug-interface-access/namesearchoptions.md) numaralandırma tek başına veya birlikte kullanılabilir.  
  
 `address`  
 [in] Sanal adres belirtir.  
  
 `ppResult`  
 [out] Döndürür bir [Idiaenumsymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) alt simge listesini içeren nesne alındı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` simgenin en az bir alt bulunamadı ya da döndürür `S_FALSE` alt öğesi bulundu; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Döndürülen yerel semboller dinamik aralık bilgileri içerir.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia100.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md)   
 [Idiaenumsymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [Idiasession::findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [NameSearchOptions numaralandırması](../../debugger/debug-interface-access/namesearchoptions.md)