---
title: Idiareadexeatoffsetcallback | Microsoft Docs
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
- IDiaReadExeAtOffsetCallback interface
ms.assetid: 3c961641-3ce3-4bc3-bd6e-a802fa3bec49
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7c88a0a359b7bd589d634cc00459b1f0f40cc19e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690403"
---
# <a name="idiareadexeatoffsetcallback"></a>IDiaReadExeAtOffsetCallback
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiareadexeatoffsetcallback](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiareadexeatoffsetcallback).  
  
Belirtilen yürütülebilir bir dosyanın dosya konumuna göre bayt sağlamak bir istemci uygulaması sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaReadExeAtOffsetCallback : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaReadExeAtOffsetCallback`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IDiaReadExeAtOffsetCallback::ReadExecutableAt](../../debugger/debug-interface-access/idiareadexeatoffsetcallback-readexecutableat.md)|Belirtilen sayıda baytı bir yürütülebilir dosya öğesinden belirtilen bir uzaklık başlayarak okur.|  
  
## <a name="remarks"></a>Açıklamalar  
 İstemci uygulama, mutlak bir uzaklık yürütülebilir dosyası dosyasına kullanan yürütülebilir dosya baytını sağlamak için bu arabirimi uygular. Bir göreli sanal adres kullanmak için uygulama [Idiareadexeatrvacallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md) arabirimi.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu yöntem istemci uygulaması tarafından uygulanan ve geçirilen [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) dosya okuma için alternatif bir yöntem olarak yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Dia2.h  
  
 Kitaplık: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)



