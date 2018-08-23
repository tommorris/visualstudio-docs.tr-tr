---
title: Idiaaddressmap::set_addressmap | Microsoft Docs
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
- IDiaAddressMap::set_addressMap method
ms.assetid: 81e82073-089b-43d5-af39-49d7a4907c7a
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 497f6ec783388c007075eed93e270a0126334605
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684374"
---
# <a name="idiaaddressmapsetaddressmap"></a>IDiaAddressMap::set_addressMap
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiaaddressmap::set_addressmap](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaaddressmap-set-addressmap).  
  
Görüntü düzen çevirileri desteklemek için bir adres Haritası sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT set_addressMap (   
   DWORD                     cbData,  
   struct DiaAddressMapEntry data[],  
   BOOL                      imagetoSymbols  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cbData`  
 [in] İçindeki öğelerin sayısını `data` parametresi.  
  
 `data[]`  
 [in] Bir dizi [DiaAddressMapEntry yapısı](../../debugger/debug-interface-access/diaaddressmapentry.md) çevirisi eşlemesini tanımlayan yapılar.  
  
 `imagetoSymbols`  
 [in] `TRUE` varsa `data` parametre (hata ayıklama sembolleri tarafından açıklandığı gibi) yeni görüntü düzen bir eşlemden özgün düzene tanımlar. `FALSE` varsa `data` özgün düzenden yapılan yeni görüntü düzen haritasıdır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Genellikle, DIA adres çevirisi haritalar program veritabanı (.pdb) dosyasından alır. Bu değerleri eksikse [Idiaaddressmap::set_imageheaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md) yöntemi iki kez çağrılır kez `imagetoSymbols` parametresini `TRUE` ve bir kez `imagetoSymbols` parametresini `FALSE`. Adres eşlemesi çevirileri kullanarak etkinleştirilemez [Idiaaddressmap::put_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md) yöntemi sürece her iki çeviri haritalar sağlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DiaAddressMapEntry yapısı](../../debugger/debug-interface-access/diaaddressmapentry.md)   
 [Idiaaddressmap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap::put_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)   
 [IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)



