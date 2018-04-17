---
title: Idiaenumdebugstreamdata::Item | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumDebugStreamData::Item method
ms.assetid: 761e61a5-44a6-4d5d-a98e-c2e9b89d2343
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6e9a929c73b3bad05e22a02dfb5d7cb28224b7f6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiaenumdebugstreamdataitem"></a>IDiaEnumDebugStreamData::Item
Belirtilen kayıt alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT Item (   
   DWORD  index,  
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 dizin  
 [in] Alınacak kayıt dizini. Aralıktaki 0 dizinidir `count`-1, burada `count` tarafından döndürülen [Idiaenumdebugstreamdata::get_Count](../../debugger/debug-interface-access/idiaenumdebugstreamdata-get-count.md).  
  
 cbData  
 [in] Veri arabelleğinin bayt cinsinden boyutu.  
  
 pcbData  
 [out] Döndürülen bayt sayısını döndürür. Varsa `data` olan `NULL`, ardından `pcbData` bayt veri belirtilen kaydında kullanılabilir toplam sayısını içerir.  
  
 veri]  
 [out] Hata ayıklama akışı kayıt veri bilgileriyle doldurulan bir arabellek.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Döndürür `E_INVALIDARG` geçersiz parametreler için ve `index` parametredir sınırların dışında.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumdebugstreamdata](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)   
 [Idiaenumdebugstreamdata::Next](../../debugger/debug-interface-access/idiaenumdebugstreamdata-next.md)   
 [Idiaenumdebugstreams::Item](../../debugger/debug-interface-access/idiaenumdebugstreams-item.md)   
 [Idiaenumdebugstreamdata::get_Count](../../debugger/debug-interface-access/idiaenumdebugstreamdata-get-count.md)   
 [IDiaEnumDebugStreamData::Skip](../../debugger/debug-interface-access/idiaenumdebugstreamdata-skip.md)