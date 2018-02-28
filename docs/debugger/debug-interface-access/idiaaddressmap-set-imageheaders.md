---
title: Idiaaddressmap::set_imageheaders | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::set_imageHeaders method
ms.assetid: a46b9d0e-43e6-433f-b2c7-aa203981e4e4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 74556e2e67478cef9b495d3740dc910b62cc8293
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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