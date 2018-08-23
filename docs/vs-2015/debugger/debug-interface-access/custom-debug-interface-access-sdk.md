---
title: Özel (hata ayıklama arabirimi Erişim SDK'sı) | Microsoft Docs
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
- Custom symbol
ms.assetid: a219fc83-d2a8-4bc5-b7e1-bfafeb247f16
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 81889dda51c603b7a4e1c56805efb657108b9a5d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688026"
---
# <a name="custom-debug-interface-access-sdk"></a>Özel (Arabirim Erişimi SDK'sında Hata Ayıklama)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [özel (arabirim erişimi SDK'ı hata ayıklama)](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/custom-debug-interface-access-sdk).  
  
Bazı derleyiciler herhangi standart sözcük Simge türlerinin tanımlanmamış sembol tanıtır. Bu simgeleri tarafından tanımlanan bir `SymTagCustom` etiketi.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda bu sembol türü için geçerli olan özellikleri gösterir.  
  
|Özellik|Veri türü|Açıklama|  
|--------------|---------------|-----------------|  
|[IDiaSymbol::get_dataBytes](../../debugger/debug-interface-access/idiasymbol-get-databytes.md)|`BYTE`|Simgeyle ilişkilendirilen veri dizisi.|  
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|Sembol, dizin kimliği.|  
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Döndürür `SymTagCustom` (biri [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) değerler).|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Simge Türlerinin Sözcük Hiyerarşisi](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)



