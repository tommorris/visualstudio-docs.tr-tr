---
title: Idiareadexeatrvacallback | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaReadExeAtRVACallback interface
ms.assetid: b2892513-3952-4f99-9b98-60cb9b1fdc91
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 09a570f27200dc677d292d645973fae8f9460f95
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiareadexeatrvacallback"></a>IDiaReadExeAtRVACallback
Yürütülebilir bir dosyanın göreli sanal adres tarafından belirtilen bayt sağlamak bir istemci uygulaması sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaReadExeAtRVACallback : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaReadExeAtRVACallback`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Idiareadexeatrvacallback::readexecutableatrva](../../debugger/debug-interface-access/idiareadexeatrvacallback-readexecutableatrva.md)|Belirtilen sayıda baytı belirtilen göreli sanal adresinden (RAV) yürütülebilir dosyası başlayarak okur.|  
  
## <a name="remarks"></a>Açıklamalar  
 İstemci uygulaması çalıştırılabilir programın dosyasına göreli sanal bir adresi kullanarak yürütülebilir dosyanın bayt sağlamak için bu arabirimi uygular. Mutlak dosya uzaklığı kullanmak için uygulama [Idiareadexeatoffsetcallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md) arabirimi.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu yöntem istemci uygulaması tarafından uygulanan ve geçirilen [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) dosya okuma için alternatif bir yöntem olarak yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [Idiareadexeatoffsetcallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)