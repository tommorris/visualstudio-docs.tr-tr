---
title: CV_access_e | Microsoft Docs
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
- CV_access_e enumeration
ms.assetid: 33c05d65-abb4-4800-a382-54a3805ea7b0
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5096c90727a1c8ffcf871853d1f59610a2baff37
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677432"
---
# <a name="cvaccesse"></a>CV_access_e
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CV_access_e](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/cv-access-e).  
  
Görünürlüğü (erişim düzeyi) üye işlevleri ve değişkenler kapsamını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
typedef enum CV_access_e {   
   CV_private   = 1,  
   CV_protected = 2,  
   CV_public    = 3  
} CV_access_e;  
```  
  
## <a name="elements"></a>Öğeleri  
 CV_private  
 Üye, özel erişimi vardır.  
  
 CV_protected  
 Üye erişimi ile korumaya aldı.  
  
 CV_public  
 Üye erişimine sahiptir.  
  
## <a name="remarks"></a>Açıklamalar  
 `friend` Erişim belirticisi değil dahil burada çünkü genellikle sınıfın özel ve korumalı öğelerine erişimi olmayan üye işlevleri tarafından kullanılıyor. Kullanım [Idiasymbol::get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md) ile simgeleri bulmak için yöntem `SymTagFriend` erişim.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: cvconst.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri ve yapıları](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Idiasymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)   
 [IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)



