---
title: Idiareadexeatoffsetcallback | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaReadExeAtOffsetCallback interface
ms.assetid: 3c961641-3ce3-4bc3-bd6e-a802fa3bec49
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aaeee00b1e077a587d33e5b1362dda666fcae698
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiareadexeatoffsetcallback"></a>IDiaReadExeAtOffsetCallback
Belirtilen yürütülebilir bir dosyanın dosya konumuna göre bayt sağlamak bir istemci uygulaması sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaReadExeAtOffsetCallback : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaReadExeAtOffsetCallback`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Idiareadexeatoffsetcallback::readexecutableat](../../debugger/debug-interface-access/idiareadexeatoffsetcallback-readexecutableat.md)|Belirtilen sayıda baytı yürütülebilir bir dosyanın belirtilen uzaklığı başlayarak okur.|  
  
## <a name="remarks"></a>Açıklamalar  
 İstemci uygulaması, mutlak bir uzaklık çalıştırılabilir programın dosyasına kullanarak yürütülebilir dosyanın bayt sağlamak için bu arabirimi uygular. Göreli sanal adresi kullanmak için uygulama [Idiareadexeatrvacallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md) arabirimi.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu yöntem istemci uygulaması tarafından uygulanan ve geçirilen [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) dosya okuma için alternatif bir yöntem olarak yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [Idiareadexeatrvacallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)