---
title: CV_access_e | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CV_access_e enumeration
ms.assetid: 33c05d65-abb4-4800-a382-54a3805ea7b0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 35b10f8a98284fdec9e94043a4b827fab226d3aa
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31457933"
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