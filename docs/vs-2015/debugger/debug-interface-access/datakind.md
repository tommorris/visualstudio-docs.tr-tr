---
title: DataKind | Microsoft Docs
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
- DataKind enumeration
ms.assetid: b64be708-22d6-4360-99e7-8f4e6b196de7
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 25d560012ae51a039572cfc3bd7a53e10fb1175d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693171"
---
# <a name="datakind"></a>DataKind
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [DataKind](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/datakind).  
  
Veri değeri belirli kapsamını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
enum DataKind {   
   DataIsUnknown,  
   DataIsLocal,  
   DataIsStaticLocal,  
   DataIsParam,  
   DataIsObjectPtr,  
   DataIsFileStatic,  
   DataIsGlobal,  
   DataIsMember,  
   DataIsStaticMember,  
   DataIsConstant  
};  
```  
  
## <a name="elements"></a>Öğeleri  
 DataIsUnknown  
 Veri sembol belirlenemiyor.  
  
 DataIsLocal  
 Veri öğesi yerel bir değişkendir.  
  
 DataIsStaticLocal  
 Statik bir yerel değişken veri öğesidir.  
  
 DataIsParam  
 Biçimsel parametre veri öğesidir.  
  
 DataIsObjectPtr  
 Veri öğesi olan bir nesne işaretçisi (`this`).  
  
 DataIsFileStatic  
 Veri öğesi dosya kapsamlı bir değişkendir.  
  
 DataIsGlobal  
 Veri öğesi genel bir değişkendir.  
  
 DataIsMember  
 Bir nesne üye değişkeni veri öğesidir.  
  
 DataIsStaticMember  
 Veri öğesi bir sınıfın statik değişkendir.  
  
 DataIsConstant  
 Veri öğesi, bir sabit değerdir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sabit listesi değerleri tarafından döndürülen [Idiasymbol::get_datakind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: cvconst.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri ve yapıları](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)



