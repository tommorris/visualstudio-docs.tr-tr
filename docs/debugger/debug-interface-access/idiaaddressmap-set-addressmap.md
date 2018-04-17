---
title: Idiaaddressmap::set_addressmap | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::set_addressMap method
ms.assetid: 81e82073-089b-43d5-af39-49d7a4907c7a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 861bcce094765e18b7fce94b6477c1520e32826b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiaaddressmapsetaddressmap"></a>IDiaAddressMap::set_addressMap
Görüntü düzeni çevirileri desteklemek için bir adres eşlemesi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT set_addressMap (   
   DWORD                     cbData,  
   struct DiaAddressMapEntry data[],  
   BOOL                      imagetoSymbols  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cbData`  
 [in] Öğe sayısı `data` parametresi.  
  
 `data[]`  
 [in] Bir dizi [DiaAddressMapEntry yapısı](../../debugger/debug-interface-access/diaaddressmapentry.md) çevirisi eşlemesini tanımla yapıları.  
  
 `imagetoSymbols`  
 [in] `TRUE` varsa `data` parametre (hata ayıklama simgeleri tarafından açıklandığı gibi) yeni resmi düzeni eşlemesinden özgün Düzen tanımlar. `FALSE` varsa `data` özgün düzeninden geçen yeni görüntü düzen eşlemesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Genellikle, DIA adres çevirisi eşlemeleri program veritabanı (.pdb) dosyasından alır. Bu değerleri eksikse [Idiaaddressmap::set_imageheaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md) yöntemi iki kez çağrıldığında kez `imagetoSymbols` parametre kümesine `TRUE` ve bir kez ile `imagetoSymbols` parametre kümesine `FALSE`. Adres eşlemesi çevirileri kullanılarak etkinleştirilemiyor [Idiaaddressmap::put_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md) yöntemi her iki çeviri eşlemeleri belirtilmediği sürece.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DiaAddressMapEntry yapısı](../../debugger/debug-interface-access/diaaddressmapentry.md)   
 [Idiaaddressmap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap::put_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)   
 [IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)