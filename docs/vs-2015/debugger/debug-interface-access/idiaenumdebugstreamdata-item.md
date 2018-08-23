---
title: Idiaenumdebugstreamdata::Item | Microsoft Docs
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
- IDiaEnumDebugStreamData::Item method
ms.assetid: 761e61a5-44a6-4d5d-a98e-c2e9b89d2343
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ee6e481cafaed07dde23ff763741eac4622b50d9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628161"
---
# <a name="idiaenumdebugstreamdataitem"></a>IDiaEnumDebugStreamData::Item
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiaenumdebugstreamdata::Item](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumdebugstreamdata-item).  
  
Belirtilen kaydı alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT Item (   
   DWORD  index,  
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 dizin  
 [in] Alınacak kaydın dizini. İçin 0 aralığındaki dizinidir `count`-1, burada `count` tarafından döndürülen [Idiaenumdebugstreamdata::get_Count](../../debugger/debug-interface-access/idiaenumdebugstreamdata-get-count.md).  
  
 cbData  
 [in] Veri arabelleğin bayt cinsinden boyutu.  
  
 pcbData  
 [out] Döndürülen bayt sayısını döndürür. Varsa `data` olduğu `NULL`, ardından `pcbData` bayt veri belirtilen kayıtta kullanılabilir toplam sayısını içerir.  
  
 veri]  
 [out] Hata ayıklama kaydı veri akışı ile doldurulmuş bir arabellek.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Döndürür `E_INVALIDARG` geçersiz parametreler için ve `index` parametredir sınırların dışında.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumdebugstreamdata](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)   
 [Idiaenumdebugstreamdata::Next](../../debugger/debug-interface-access/idiaenumdebugstreamdata-next.md)   
 [Idiaenumdebugstreams::Item](../../debugger/debug-interface-access/idiaenumdebugstreams-item.md)   
 [Idiaenumdebugstreamdata::get_Count](../../debugger/debug-interface-access/idiaenumdebugstreamdata-get-count.md)   
 [IDiaEnumDebugStreamData::Skip](../../debugger/debug-interface-access/idiaenumdebugstreamdata-skip.md)



