---
title: Idiaenumframedata::Next | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::Next method
ms.assetid: 546e2e23-efb2-425a-96a1-808c67c519fb
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7beda616143471e505d1edb04d196225687bce6a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiaenumframedatanext"></a>IDiaEnumFrameData::Next
Çerçeve veri öğeleri numaralandırması dizisinde belirtilen sayısını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT Next (   
   ULONG           celt,   
   IDiaFrameData** rgelt,  
   ULONG*          pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 celt  
 [in] Alınacak Numaralandırıcı çerçeve veri öğe sayısı.  
  
 rgelt  
 [out] Bir dizi [Idiaframedata](../../debugger/debug-interface-access/idiaframedata.md) istenen çerçeve veri öğeleri ile doldurulacak nesneleri.  
  
 pceltFetched  
 [out] Çerçeve veri öğelerinin getirilen Numaralandırıcı döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`. Döndürür `S_FALSE` olması durumunda daha fazla kayıt yok. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumframedata](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)