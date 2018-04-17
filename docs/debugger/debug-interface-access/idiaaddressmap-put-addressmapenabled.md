---
title: Idiaaddressmap::put_addressmapenabled | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::put_addressMapEnabled method
ms.assetid: 0f205337-4e59-4383-8059-7b1d207d6dcd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a9d81a9204987348f7664f53c1873ddbbfc62cf0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiaaddressmapputaddressmapenabled"></a>IDiaAddressMap::put_addressMapEnabled
Adres eşlemesi simgesi adresleri çevirmek için kullanılması gerekip gerekmediğini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT put_addressMapEnabled (   
   BOOL NewVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 NewVal  
 [in] Kümesine `TRUE` sembolleri çevirisini etkinleştirmek için veya `FALSE` devre dışı bırakmak için.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Yürütülebilir sonrası işlemciler bazen yürütülebilir güncelleştirin. DIA yeni düzen simgelerin çeviri desteklemek için bir mekanizma içerir.  
  
 PDB dosyası yüklendiğinde dosyasında depolanan adres eşleme etkindir. Bir istemci uygulaması gerektiğinde çağırarak kendi adres eşlemesi sağlamak için zamanlar [Idiaaddressmap::set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) yöntemi. Varsa `set_addressMap` yöntemi başarılı olduğunda, istemci uygulaması çağırmalısınız `put_addressMapEnabled` yöntemi ile bir `NewVal` parametresinin `TRUE` adresi eşlenen kullanımını etkinleştirmek için.  
  
 Etkinleştirilecek adres eşlemesi geçerli durumunu çağrısıyla alınabilir [Idiaaddressmap::get_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaaddressmap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap::set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)   
 [IDiaAddressMap::get_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md)