---
title: Idiasymbol::get_hassecuritychecks | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_hasSecurityChecks method
ms.assetid: 4bb51f62-8645-41a4-bc44-1451010623fd
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8247ed4735bdd8ca4bc8e62ff4507b0aafb957e7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgethassecuritychecks"></a>IDiaSymbol::get_hasSecurityChecks
Derlenecek dosya veya işlev arabellek taşması güvenlik denetimleri ile derlendikten olup olmadığını belirten bir bayrak alır (örneğin, [/GS (arabellek güvenlik denetimi)](/cpp/build/reference/gs-buffer-security-check) derleyici anahtar).  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_hasSecurityChecks(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pFlag`  
 [out] Döndürür `TRUE` tüm güvenlik denetimleri; işlevi varsa, aksi takdirde, döndürür `FALSE`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
> [!NOTE]
>  Dönüş değeri `S_FALSE` özelliği simgesi kullanılabilir olmadığı anlamına gelir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Gereksinim|Açıklama|  
|-----------------|-----------------|  
|Başlık:|dia2.h|  
|Sürüm:|DIA SDK v8.0|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [/GS (arabellek güvenlik denetimi)](/cpp/build/reference/gs-buffer-security-check)