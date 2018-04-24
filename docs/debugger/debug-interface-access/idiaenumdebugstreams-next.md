---
title: Idiaenumdebugstreams::Next | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumDebugStreams::Next method
ms.assetid: eb8eae5a-be27-45f4-a7bd-6e4ef0652385
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 780aaca4d840d87df17572ec7d58cebc84e84d4c
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaenumdebugstreamsnext"></a>IDiaEnumDebugStreams::Next
Belirtilen bir numaralandırma sırası hata ayıklama akış sayısını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT Next (   
   ULONG                     celt,   
   IDiaEnumDebugStreamData** rgelt,  
   ULONG*                    pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 celt  
 [in] **T**kendisinin alınacak Numaralandırıcı hata ayıklama akış sayısı.  
  
 rgelt  
 [out] Bir dizi döndürür [Idiaenumdebugstreamdata](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md) debug temsil eden nesneler akışları alınıyor.  
  
 pceltFetched  
 [out] Döndürülen hata ayıklama akış sayısını döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`. Döndürür `S_FALSE` hiçbir daha fazla akışları varsa. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaEnumDebugStreams](../../debugger/debug-interface-access/idiaenumdebugstreams.md)