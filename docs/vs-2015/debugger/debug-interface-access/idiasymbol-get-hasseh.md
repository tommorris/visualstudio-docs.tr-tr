---
title: Idiasymbol::get_hasseh | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_hasSEH method
ms.assetid: 1a709ded-22c8-464c-97be-eba5e464210c
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f8dd3eda1eaf992de0b38e26bde93ae3f4c1de05
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685766"
---
# <a name="idiasymbolgethasseh"></a>IDiaSymbol::get_hasSEH
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiasymbol::get_hasseh](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-hasseh).  
  
İşlev herhangi içerip içermediğini belirten bir bayrak alır [yapılandırılmış özel durum işleme (C/C++)](http://msdn.microsoft.com/library/dd3b647d-c269-43a8-aab9-ad1458712976) (örneğin, __try /\__except bloğu).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT get_hasSEH(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pFlag`  
 [out] Döndürür `TRUE` tüm yapılandırılmış özel durum blokları; işleme işlevi varsa, aksi halde döndürür `FALSE`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya hata kodu.  
  
> [!NOTE]
>  Dönüş değeri `S_FALSE` özelliği simge için kullanılabilir değil anlamına gelir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Gereksinim|Açıklama|  
|-----------------|-----------------|  
|Üst bilgi:|dia2.h|  
|Sürüm:|DIA SDK v8.0|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [Yapılandırılmış Özel Durum İşleme (C/C++)](http://msdn.microsoft.com/library/dd3b647d-c269-43a8-aab9-ad1458712976)



