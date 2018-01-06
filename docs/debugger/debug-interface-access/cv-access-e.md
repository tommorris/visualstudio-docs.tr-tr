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
ms.workload: multiple
ms.openlocfilehash: 30914c63f5577519a7451cb6d1aee6d651161678
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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
 [IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)