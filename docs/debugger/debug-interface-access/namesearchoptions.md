---
title: NameSearchOptions | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: NameSearchOptions enumeration
ms.assetid: 67dfbede-2678-47df-b664-5c49841d0b9b
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7ceadd085a3099721e73e04dd09ea5a0b81ad1d6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="namesearchoptions"></a>NameSearchOptions
Simge ve dosya adları için arama seçeneklerini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
enum NameSearchOptions {   
   nsNone,  
   nsfCaseSensitive     = 0x1,  
   nsfCaseInsensitive   = 0x2,  
   nsfFNameExt          = 0x4,  
   nsfRegularExpression = 0x8,  
   nsfUndecoratedName   = 0x10,  
  
// For backward compatibility:  
   nsCaseSensitive           = nsfCaseSensitive,  
   nsCaseInsensitive         = nsfCaseInsensitive,  
   nsFNameExt                = nsfCaseInsensitive | nsfFNameExt,  
   nsRegularExpression       = nsfRegularExpression | nsfCaseSensitive,  
   nsCaseInRegularExpression = nsfRegularExpression | nsfCaseInsensitive  
};  
```  
  
## <a name="elements"></a>Öğeleri  
 `nsNone`  
 Hiçbir seçenek belirtildi.  
  
 `nsfCaseSensitive`  
 Büyük küçük harfe duyarlı adı eşleşir geçerlidir.  
  
 `nsfCaseInsensitive`  
 Büyük küçük harf duyarsız adı eşleşir geçerlidir.  
  
 `nsfFNameExt`  
 Adları yolları olarak değerlendirir ve DosyaAdı.uzn adı eşleşir uygular.  
  
 `nsfRegularExpression`  
 Büyük küçük harfe duyarlı adı eşleşen bir joker karakter olarak yıldız işareti (*) ve soru işareti (?) kullanarak uygular.  
  
 `nsfUndecoratedName`  
 Ve hem de adlar simgeleri geçerlidir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu numaralandırma değerleri için aşağıdaki yöntemlerden geçirilir:  
  
-   [Idiasession::findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)  
  
-   [Idiasession::findfile](../../debugger/debug-interface-access/idiasession-findfile.md)  
  
-   [Idiasymbol::findchildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: dia2.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar ve yapılar](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Idiasession::findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [Idiasession::findfile](../../debugger/debug-interface-access/idiasession-findfile.md)   
 [Idiasymbol::findchildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)