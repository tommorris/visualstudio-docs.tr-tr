---
title: Idiaaddressmap::set_imageheaders | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::set_imageHeaders method
ms.assetid: a46b9d0e-43e6-433f-b2c7-aa203981e4e4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 51b68475b9ef0374f95febabc2997524bfd61259
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaaddressmapsetimageheaders"></a>IDiaAddressMap::set_imageHeaders
Ayarlar göreli sanal adres çevirisi etkinleştirmek için üstbilgiler görüntü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT set_imageHeaders (   
   DWORD cbData,  
   BYTE  data[],  
   BOOL  originalHeaders  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 cbData  
 [in] Üstbilgi veri baytı sayısı. Olmalıdır `n*sizeof(IMAGE_SECTION_HEADER)` burada `n` bölüm üstbilgilerinde yürütülebilir dosya sayısıdır.  
  
 veri]  
 [in] Bir dizi `IMAGE_SECTION_HEADER` görüntü üst bilgileri olarak kullanılmak üzere yapıları.  
  
 originalHeaders  
 [in] Kümesine `FALSE` görüntü üstbilgileri yeni görüntüden varsa `TRUE` bir yükseltmeden önce özgün görüntü yansıtmak durumunda. Genellikle, bu ayarlanır `TRUE` çağrıları birlikte, yalnızca [Idiaaddressmap::set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) yöntemi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `IMAGE_SECTION_HEADER` Yapısı Winnt.h içinde bildirilen ve yürütülebilir görüntü bölüm başlığı biçimi temsil eder.  
  
 Göreli sanal adres hesaplamalar bağlı `IMAGE_SECTION_HEADER` değerleri. Genellikle, DIA Bu program veritabanı (.pdb) dosyasından alır. Bu değerleri eksikse DIA göreli sanal adresleri hesaplayamadı ve [Idiaaddressmap::get_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md) yöntemi döndürür `FALSE`. İstemci ardından çağırmalısınız [Idiaaddressmap::put_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md) görüntü eksik görüntü üstbilgileri sağladıktan sonra göreli sanal adres hesaplamalar etkinleştirmek için yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaaddressmap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap::set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)   
 [Idiaaddressmap::get_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)   
 [IDiaAddressMap::put_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)