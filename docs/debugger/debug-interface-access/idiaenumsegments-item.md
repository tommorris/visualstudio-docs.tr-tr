---
title: Idiaenumsegments::Item | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSegments::Item method
ms.assetid: ee44dd55-39a0-4b7b-97ff-2e1226eeb2bd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 101e44fdd5601a65421fe5f65534cac6bd8bef75
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiaenumsegmentsitem"></a>IDiaEnumSegments::Item
Bir segment yoluyla bir dizin alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT Item (   
   DWORD         index,  
   IDiaSegment** segment  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 dizin  
 [in] Dizin [Idiasegment](../../debugger/debug-interface-access/idiasegment.md) alınacak nesne. Aralıktaki 0 dizinidir `count`-1, burada `count` tarafından döndürülen [Idiaenumsegments::get_Count](../../debugger/debug-interface-access/idiaenumsegments-get-count.md) yöntemi.  
  
 Segment  
 [out] Döndürür bir [Idiasegment](../../debugger/debug-interface-access/idiasegment.md) istenen kesimini temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumsegments](../../debugger/debug-interface-access/idiaenumsegments.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)