---
title: CV_access_e | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: CV_access_e enumeration
ms.assetid: 33c05d65-abb4-4800-a382-54a3805ea7b0
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6112c72836c718dbd97ddfb62504186fdcf6ca33
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="cvaccesse"></a>CV_access_e
Üye işlevleri ve değişkenler görünürlüğünü (erişim düzeyi) kapsamını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
typedef enum CV_access_e {   
   CV_private   = 1,  
   CV_protected = 2,  
   CV_public    = 3  
} CV_access_e;  
```  
  
## <a name="elements"></a>Öğeleri  
 CV_private  
 Üye özel erişimi var.  
  
 CV_protected  
 Üye erişimi korumaya aldı.  
  
 CV_public  
 Üye genel erişimi vardır.  
  
## <a name="remarks"></a>Açıklamalar  
 `friend` Erişim belirticisi dahil değildir burada çünkü genellikle sınıfının hem özel hem de korumalı öğeleri erişimi olmayan üye işlevleri tarafından kullanılır. Kullanım [Idiasymbol::get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md) sembolleriyle bulmak için yöntem `SymTagFriend` erişim.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: cvconst.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar ve yapılar](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Idiasymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)   
 [Idiasymbol::get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)