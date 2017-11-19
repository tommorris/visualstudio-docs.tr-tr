---
title: IDiaStackWalkHelper | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackWalkHelper2 interface
ms.assetid: d66e5c84-565d-494e-8486-f91db9a34548
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4a092cc6044f42a53abf97ff36417a23c1f2adca
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiastackwalkhelper"></a>IDiaStackWalkHelper
Program hata ayıklama (.pdb) veritabanı dosyasını kullanarak yığın taramasını kolaylaştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
IDiaStackWalkHelper: IUnknown  
  
```  
  
## <a name="methods-in-vtable-order"></a>VTable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterir `IDiaStackWalkHelper`:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IDiaStackWalkHelper::get_registerValue](../../debugger/debug-interface-access/idiastackwalkhelper-get-registervalue.md)|Bir kayıt değeri alır.|  
|[IDiaStackWalkHelper::put_registerValue](../../debugger/debug-interface-access/idiastackwalkhelper-put-registervalue.md)|Bir kayıt değerini ayarlar.|  
|[IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md)|Bir veri bloğunun bellekte çalıştırılabilir programın görüntüden okur.|  
|[IDiaStackWalkHelper::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddress.md)|Belirtilen yığın çerçevesi yakın işlevi dönüş adresi arar.|  
|[Idiastackwalkhelper::searchforreturnaddressstart](../../debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddressstart.md)|Bir dönüş adresi hiç veya neredeyse belirtilen yığını adres için belirtilen yığın çerçevesi arar.|  
|[IDiaStackWalkHelper::frameForVA](../../debugger/debug-interface-access/idiastackwalkhelper-frameforva.md)|Belirtilen sanal adres içeren yığın çerçevesi alır.|  
|[Idiastackwalkhelper::symbolforva](../../debugger/debug-interface-access/idiastackwalkhelper-symbolforva.md)|Belirtilen sanal adres içeren simge alır. **Not:** simge türü olmalıdır `SymTagFunctionType` (arasında bir değer [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) numaralandırması).|  
|[IDiaStackWalkHelper::pdataForVA](../../debugger/debug-interface-access/idiastackwalkhelper-pdataforva.md)|Belirtilen sanal adresi ile ilişkili PDATA veri bloğu döndürür.|  
|[Idiastackwalkhelper::imageforva](../../debugger/debug-interface-access/idiastackwalkhelper-imageforva.md)|Bir sanal adres yere çalıştırılabilir programın bellek alanında verilen yürütülebilir başlangıç sanal adresini alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim, çalıştırılabilir program yürütülmesi sırasında yığın çerçeveleri listesini oluşturmak hakkında bilgi edinmek için DIA kodu tarafından çağrılır.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bir istemci uygulaması program yürütülmesi sırasında yığın taramasını desteklemek için bu arabirimi uygular. Bu arabirim örneği geçirilir [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md) veya [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md) yöntemleri.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaframedata](../../debugger/debug-interface-access/idiaframedata.md)   
 [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)   
 [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)