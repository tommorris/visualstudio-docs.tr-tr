---
title: Idiastackwalkframe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame interface
ms.assetid: 42d82845-d6f6-4846-9ecd-9dd169216077
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5e532323923aaa3c50e00fc685fb39eaf8bfed80
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiastackwalkframe"></a>IDiaStackWalkFrame
Yığın bağlamı çağırmaları arasında tutar [Idiaframedata::Execute](../../debugger/debug-interface-access/idiaframedata-execute.md) yöntemi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaStackWalkFrame : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaStackWalkFrame`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IDiaStackWalkFrame::get_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-get-registervalue.md)|Bir kayıt değeri alır.|  
|[IDiaStackWalkFrame::put_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-put-registervalue.md)|Bir kayıt değerini ayarlar.|  
|[IDiaStackWalkFrame::readMemory](../../debugger/debug-interface-access/idiastackwalkframe-readmemory.md)|Bellek görüntüden okur.|  
|[IDiaStackWalkFrame::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddress.md)|Belirtilen yığın çerçevesi yakın işlevi dönüş adresi arar.|  
|[IDiaStackWalkFrame::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddressstart.md)|Bir dönüş adresi hiç veya neredeyse belirtilen adres için belirtilen yığın çerçevesi arar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim program yürütülmesi sırasında okuma ve kayıtları yazma yanı sıra bellek erişmek ve dönüş adresleri bulmak için kullanılır.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 İstemci uygulaması bu arabirimi uygular ve arabirimine örneği geçirir [Idiaframedata::Execute](../../debugger/debug-interface-access/idiaframedata-execute.md) yöntemi. Bu arabirim aynı örneği yeniden her çağrılması sırasında kasalar durumunu korumak için kullanılan `execute` yöntemi. `execute` Yöntemi de bu arabirim dönüş adresi belirlemek için kullanır.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaFrameData::execute](../../debugger/debug-interface-access/idiaframedata-execute.md)