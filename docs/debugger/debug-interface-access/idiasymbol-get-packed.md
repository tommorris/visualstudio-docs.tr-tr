---
title: Idiasymbol::get_packed | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_packed method
ms.assetid: e42ff368-56c4-49a2-8676-f80e349efa21
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f124a27bb05e77d52bebde9f97dc81ea1fc971bc
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasymbolgetpacked"></a>IDiaSymbol::get_packed
Kullanıcı tanımlı veri türü (UDT) dolu olup olmadığını belirten bir bayrak alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_packed (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Döndürür `TRUE` UDT paketlenmiş; Aksi halde, döndürür `FALSE`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
> [!NOTE]
>  Dönüş değeri `S_FALSE` özelliği simgesi kullanılabilir olmadığı anlamına gelir.  
  
## <a name="remarks"></a>Açıklamalar  
 Paketlenmiş UDT tüm üyeleri olarak birbirine yakın mümkün olduğunca bellek sınırları hizalamak için karışan dolgu ile konumlandırılmış anlamına gelir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)