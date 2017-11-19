---
title: Idialoadcallback | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaLoadCallback interface
ms.assetid: 2f18c64c-2cf0-43fc-a447-21e82702ca2a
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7dc5034967fe94b8be6503a9c86f7b6bc6ee14ed
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idialoadcallback"></a>IDiaLoadCallback
Geri aramalar yordamı bulma, böylece konumu girişimi ilerlemesini bildirmek bir kullanıcı arabirimi etkinleştirme DIA simge alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaLoadCallback : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki yöntemlerden bu arabirim tarafından sunulur:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Idialoadcallback::notifydebugdir](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md)|Hata ayıklama dizin .exe dosyasında bulunan çağrılır.|  
|[Idialoadcallback::notifyopendbg](../../debugger/debug-interface-access/idialoadcallback-notifyopendbg.md)|Aday .dbg Dosya açıldığında çağrılır.|  
|[Idialoadcallback::notifyopenpdb](../../debugger/debug-interface-access/idialoadcallback-notifyopenpdb.md)|Aday .pdb dosyasını açıldığında çağrılır.|  
|[Idialoadcallback::restrictregistryaccess](../../debugger/debug-interface-access/idialoadcallback-restrictregistryaccess.md)|Kayıt defteri sorguları sembol arama yolları bulmak için kullanılan varsa belirler.|  
|[Idialoadcallback::restrictsymbolserveraccess](../../debugger/debug-interface-access/idialoadcallback-restrictsymbolserveraccess.md)|Erişim simgesi sunucuya simgeleri çözümlemek için izin verilip verilmediğini belirler.|  
  
## <a name="remarks"></a>Açıklamalar  
 İstemci uygulaması bu arabirimi uygular ve kendisine bir başvuru çağrısında sağlar [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) yöntemi.  
  
 Bir yükleme işlemi uygulanan ek kısıtlamalar için bkz: [Idialoadcallback2](../../debugger/debug-interface-access/idialoadcallback2.md) arabirimi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [Idiareadexeatoffsetcallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)   
 [Idiareadexeatrvacallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [Idialoadcallback2](../../debugger/debug-interface-access/idialoadcallback2.md)