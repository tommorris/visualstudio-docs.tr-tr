---
title: Idiaenumframedata::Skip | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::Skip method
ms.assetid: 67140b4c-7125-4895-932d-42412326da29
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9d33a83fff2d09cd2c0a9c74a71ee4ce10a52fd7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiaenumframedataskip"></a>IDiaEnumFrameData::Skip
Çerçeve veri öğeleri bir numaralandırma dizisinde belirtilen sayıda atlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT Skip (   
   ULONG celt  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 celt  
 [in] Çerçeve veri öğeleri atlamak için numaralandırma dizisindeki sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` atlamak için daha fazla kayıt varsa.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)