---
title: Idiaımagedata::get_imagebase | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaImageData::get_imageBase method
ms.assetid: 4ba3d9e4-b205-4ee6-a41d-6996972f1f85
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9cd7cb16a4f6a6a629102eafbc212e4b2fff0f00
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaimagedatagetimagebase"></a>IDiaImageData::get_imageBase
Görüntü tabanlı burada bellek konumunu alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_imageBase (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Önerilen görüntü taban değeri döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Yüklendiğinde görüntü temel çakışmalar nedeniyle görüntünün otomatik olarak bir kullanılmayan bellek konumuna rebased. Bu yöntem modülünde derleme zamanında depolanan temel İpucu (önerilen bellek konumuna) döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaImageData](../../debugger/debug-interface-access/idiaimagedata.md)