---
title: Idiastackwalkframe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackWalkFrame interface
ms.assetid: 42d82845-d6f6-4846-9ecd-9dd169216077
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: be50964aaadad30aa13d6627be2ad1637e6123b3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
|[Idiastackwalkframe::get_registervalue](../../debugger/debug-interface-access/idiastackwalkframe-get-registervalue.md)|Bir kayıt değeri alır.|  
|[Idiastackwalkframe::put_registervalue](../../debugger/debug-interface-access/idiastackwalkframe-put-registervalue.md)|Bir kayıt değerini ayarlar.|  
|[Idiastackwalkframe::readmemory](../../debugger/debug-interface-access/idiastackwalkframe-readmemory.md)|Bellek görüntüden okur.|  
|[Idiastackwalkframe::searchforreturnaddress](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddress.md)|Belirtilen yığın çerçevesi yakın işlevi dönüş adresi arar.|  
|[Idiastackwalkframe::searchforreturnaddressstart](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddressstart.md)|Bir dönüş adresi hiç veya neredeyse belirtilen adres için belirtilen yığın çerçevesi arar.|  
  
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
 [Idiaframedata::Execute](../../debugger/debug-interface-access/idiaframedata-execute.md)