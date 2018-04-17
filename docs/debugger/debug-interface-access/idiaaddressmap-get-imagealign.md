---
title: Idiaaddressmap::get_imagealign | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::get_imageAlign method
ms.assetid: f1ba8071-669c-4cf7-9ac0-02f26d99f366
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c37d05025f6de870d6011e2abba31cd28f06f780
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiaaddressmapgetimagealign"></a>IDiaAddressMap::get_imageAlign
Geçerli resmi hizalaması alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_imageAlign (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Görüntü hizalama değeri yürütülebilir dosyadan döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Görüntüleri görüntünün nasıl yüklenir ve oluşturulan bağlı olarak belirli bellek sınırları hizalanır. Hizalama genellikle 1, 2, 4, 8, 16, 32 veya 64 baytlık sınırları'dır. Resmi hizalaması çağrısıyla ayarlanabilir [Idiaaddressmap::put_imagealign](../../debugger/debug-interface-access/idiaaddressmap-put-imagealign.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaaddressmap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaAddressMap::put_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-put-imagealign.md)