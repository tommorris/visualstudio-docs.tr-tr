---
title: Idialoadcallback | Microsoft Docs
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
- IDiaLoadCallback interface
ms.assetid: 2f18c64c-2cf0-43fc-a447-21e82702ca2a
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9a77a14ba09d7bd4f6fa0d3971f6422353eb40b1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686617"
---
# <a name="idialoadcallback"></a>IDiaLoadCallback
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idialoadcallback](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idialoadcallback).  
  
Yordamı bulmak, bu nedenle konumu denemesinin ilerleme üzerinde rapor için bir kullanıcı arabirimi etkinleştirme DIA Sembol'nden geri çağırmaları alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaLoadCallback : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki yöntemleri bu arabirim tarafından sunulur:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IDiaLoadCallback::NotifyDebugDir](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md)|Hata ayıklama dizini .exe dosyasında bulundu çağrılır.|  
|[IDiaLoadCallback::NotifyOpenDBG](../../debugger/debug-interface-access/idialoadcallback-notifyopendbg.md)|Bir aday .dbg Dosya açıldığında çağrılır.|  
|[IDiaLoadCallback::NotifyOpenPDB](../../debugger/debug-interface-access/idialoadcallback-notifyopenpdb.md)|Bir aday .pdb dosyası açıldığında çağrılır.|  
|[IDiaLoadCallback::RestrictRegistryAccess](../../debugger/debug-interface-access/idialoadcallback-restrictregistryaccess.md)|Kayıt defteri sorguları sembol arama yollarını bulmak için kullanılabilir olmadığını belirler.|  
|[IDiaLoadCallback::RestrictSymbolServerAccess](../../debugger/debug-interface-access/idialoadcallback-restrictsymbolserveraccess.md)|Erişim bir simge sunucusuna simgeleri çözme izin verilip verilmediğini belirler.|  
  
## <a name="remarks"></a>Açıklamalar  
 İstemci uygulaması bu arabirimi uygulayan ve çağrısında ona başvuru sağlayan [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) yöntemi.  
  
 Bir yükleme işlemi uygulanan ek kısıtlamaları için bkz: [Idialoadcallback2](../../debugger/debug-interface-access/idialoadcallback2.md) arabirimi.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Dia2.h  
  
 Kitaplık: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [Idiareadexeatoffsetcallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)   
 [Idiareadexeatrvacallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)



