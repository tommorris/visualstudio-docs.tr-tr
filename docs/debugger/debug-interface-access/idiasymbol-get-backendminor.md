---
title: Idiasymbol::get_backendminor | Microsoft Docs
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
- IDiaSymbol::get_backEndMinor method
ms.assetid: 37f38d19-6685-440d-a477-7127c4f8699e
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: dad2d2ac3cd5ff1ed57f71b3858db7cfa6875178
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetbackendminor"></a>IDiaSymbol::get_backEndMinor
Derleyici arka uç alt sürüm numarasını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_backEndMinor (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Arka uç alt sürüm numarasını döndürür. Açıklamalar bakın.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
> [!NOTE]
>  Dönüş değeri `S_FALSE` özelliği simgesi kullanılabilir olmadığı anlamına gelir.  
  
## <a name="remarks"></a>Açıklamalar  
 Derleyici genellikle iki birincil öğeden oluşur: kaynak koduna bir ara forma ayrıştırma işleyen, ön uç (ayrıştırıcı) ve derlemeye Ara formun dönüştüren bir arka uç (Kod Oluşturucu). Seyrek için ön uç arka uçtan farklı bir sürüme sahip değil.  
  
 Bir ön uç veya arka uç sürüm numarası üç bölümden oluşur: \<ana >.\< İkincil >. \<Yapı > Burada \<ana > ana sürüm numarası \<küçük > ikincil sürüm numarası ve \<Yapı > yapı numarasıdır. Örneğin, 13.10.3077.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Gereksinim|Açıklama|  
|-----------------|-----------------|  
|Başlık:|dia2.h|  
|Sürüm:|DIA SDK v7.0|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)