---
title: IDiaStackWalkHelper | Microsoft Docs
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
- IDiaStackWalkHelper2 interface
ms.assetid: d66e5c84-565d-494e-8486-f91db9a34548
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a8af7a0f463fc5d2089b374ac881cd0089dce0c1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694664"
---
# <a name="idiastackwalkhelper"></a>IDiaStackWalkHelper
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDiaStackWalkHelper](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackwalkhelper).  
  
Program hata ayıklama veritabanı (.pdb) dosyası kullanarak yığınını walking kolaylaştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
IDiaStackWalkHelper: IUnknown  
  
```  
  
## <a name="methods-in-vtable-order"></a>VTable sırayla yöntemleri  
 Yöntemleri, aşağıdaki tabloda gösterilmiştir `IDiaStackWalkHelper`:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IDiaStackWalkHelper::get_registerValue](../../debugger/debug-interface-access/idiastackwalkhelper-get-registervalue.md)|Bir kayıt değeri alır.|  
|[IDiaStackWalkHelper::put_registerValue](../../debugger/debug-interface-access/idiastackwalkhelper-put-registervalue.md)|Bir kayıt değeri ayarlar.|  
|[IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md)|Bir veri bloğu bellek yürütülebilir dosyası görüntüden okur.|  
|[IDiaStackWalkHelper::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddress.md)|Belirtilen yığın çerçevesinin yakın işlevi dönüş adresi arar.|  
|[IDiaStackWalkHelper::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddressstart.md)|Belirtilen yığın çerçevesinin dönüş adresi veya belirtilen yığın adresi yakın arar.|  
|[IDiaStackWalkHelper::frameForVA](../../debugger/debug-interface-access/idiastackwalkhelper-frameforva.md)|Belirtilen sanal adres içeren yığın çerçevesini alır.|  
|[IDiaStackWalkHelper::symbolForVA](../../debugger/debug-interface-access/idiastackwalkhelper-symbolforva.md)|Belirtilen sanal adres içeren simgeyi alır. **Not:** sembol türü olmalıdır `SymTagFunctionType` (arasında bir değer [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) sabit listesi).|  
|[IDiaStackWalkHelper::pdataForVA](../../debugger/debug-interface-access/idiastackwalkhelper-pdataforva.md)|Belirtilen sanal adresle ilişkilendirilen PDATA veri bloğu döndürür.|  
|[IDiaStackWalkHelper::imageForVA](../../debugger/debug-interface-access/idiastackwalkhelper-imageforva.md)|Sanal adresi yere bellek alanı yürütülebilir dosyası içinde belirtilen bir yürütülebilir dosyanın sanal başlangıç adresi alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim, program yürütme sırasında yığın çerçevelerini listesini oluşturmak için yürütülebilir dosya hakkında bilgi edinmek için DIA kod tarafından çağrılır.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bir istemci uygulaması, program yürütme sırasında yığın walking desteklemek için bu arabirimi uygular. Bu arabirim örneğini geçirilir [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md) veya [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md) yöntemleri.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Dia2.h  
  
 Kitaplık: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaframedata](../../debugger/debug-interface-access/idiaframedata.md)   
 [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)   
 [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)



