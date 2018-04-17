---
title: Idiaaddressmap::put_relativevirtualaddressenabled | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::put_relativeVirtualAddressEnabled method
ms.assetid: 767c078e-8ad7-4940-9e00-cae7704aadee
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 97dc30db5c11948c97359f7e2a888d78106a1996
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiaaddressmapputrelativevirtualaddressenabled"></a>IDiaAddressMap::put_relativeVirtualAddressEnabled
Etkinleştirmek veya hesaplama ve göreli sanal adresleri (RAV) kullanımını devre dışı bırakmak istemcinin verir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT put_relativeVirtualAddressEnabled (   
   BOOL NewVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 NewVal  
 [in] Kümesine `TRUE` etkinleştirmek için veya `FALSE` devre dışı bırakmak için.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Adresleri DIA arabirimleri tarafından ve çalıştırılabilir programın görüntü temel, göreli açıklanan hata ayıklama nesneleri için göreli sanal adresler olarak alınabilir.  
  
 Segment başlangıçta PDB dosyadan yüklendiğinde RVAs kullanımını etkinleştirilir. RVAs kullanımını geçerli durumunu almak için çağrı [Idiaaddressmap::get_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md) yöntemi.  
  
 `put_relativeVirtualAddress` Yöntemi çağrılır, başarılı bir çağrı sonra RVAs etkinleştirmek için [Idiaaddressmap::set_imageheaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md) yöntemi yeni görüntü üstbilgileri kurulan.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaaddressmap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap::get_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)   
 [IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)