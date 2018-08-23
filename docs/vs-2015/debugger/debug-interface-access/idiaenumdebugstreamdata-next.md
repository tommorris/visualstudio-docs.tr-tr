---
title: Idiaenumdebugstreamdata::Next | Microsoft Docs
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
- IDiaEnumDebugStreamData::Next method
ms.assetid: 114171dd-38fd-4bd7-a702-8ff887ffc99b
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 54b72aa6b81afeabc4eee9849dba2fba0cc0f5b3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629767"
---
# <a name="idiaenumdebugstreamdatanext"></a>IDiaEnumDebugStreamData::Next
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiaenumdebugstreamdata::Next](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumdebugstreamdata-next).  
  
Belirtilen sayıda numaralandırılan sıralı kayıtları alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT Next (   
   ULONG  celt,  
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[],  
   ULONG* pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 celt  
 [in] Alınacak kayıt sayısı.  
  
 cbData  
 [in] Veri arabelleğin bayt cinsinden boyutu.  
  
 pcbData  
 [out] Döndürülen bayt sayısını döndürür. Varsa `data` NULL ise `pcbData` tüm kayıtları istenen bayt veri kullanılabilir toplam sayısını içerir.  
  
 veri]  
 [out] Hata ayıklama akışı kaydı veri ile doldurulacak olan bir arabellek.  
  
 pceltFetched  
 [out içinde] Kayıt sayısını döndürür `data`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`. Döndürür `S_FALSE` daha fazla kayıt varsa. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumdebugstreamdata](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)   
 [IDiaEnumDebugStreams::Next](../../debugger/debug-interface-access/idiaenumdebugstreams-next.md)



