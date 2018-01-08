---
title: Idiasymbol::get_hassetjump | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_hasSetJump method
ms.assetid: 22656206-dccf-40ed-b179-fc016d1b262a
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d6d7141e6dd97fbe4c1d7b3df9a2d245e2abe3d4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgethassetjump"></a>IDiaSymbol::get_hasSetJump
İşlevi bir kullanımını içeren olup olmadığını belirten bir bayrak alır [setjmp](/cpp/c-runtime-library/reference/setjmp) komutu (ile eşleştirilmiş [longjmp](/cpp/c-runtime-library/reference/longjmp) komutu, bu form C tarzı yöntemi özel durum işleme).  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_hasSetJump(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pFlag`  
 [out] Döndürür `TRUE` işlevi içeriyorsa, bir `setjmp` ; Aksi halde, döndürür komutu `FALSE`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya hata kodu.  
  
> [!NOTE]
>  Dönüş değeri `S_FALSE` özelliğin simge için kullanılabilir olup olmadığı anlamına gelir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Gereksinim|Açıklama|  
|-----------------|-----------------|  
|Başlık:|dia2.h|  
|Sürüm:|DIA SDK v8.0|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [Idiasymbol::get_haslongjump](../../debugger/debug-interface-access/idiasymbol-get-haslongjump.md)   
 [longjmp](/cpp/c-runtime-library/reference/longjmp)   
 [setjmp](/cpp/c-runtime-library/reference/setjmp)