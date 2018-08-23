---
title: Idiaımagedata::get_imagebase | Microsoft Docs
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
- IDiaImageData::get_imageBase method
ms.assetid: 4ba3d9e4-b205-4ee6-a41d-6996972f1f85
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 278ea226c9531cdf16cc7660bb4eba67860430a4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693043"
---
# <a name="idiaimagedatagetimagebase"></a>IDiaImageData::get_imageBase
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiaımagedata::get_imagebase](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaimagedata-get-imagebase).  
  
Görüntü tabanlı burada bellek konumunu alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT get_imageBase (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Önerilen görüntü temel değeri döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Yüklendiğinde görüntü temel çakışmalar nedeniyle görüntü otomatik olarak bir kullanılmayan bellek konumuna ReBase işlemi gerçekleştirildi. Bu yöntem, derleme zamanında modülünde depolanmış temel İpucu (önerilen bellek konumu) döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaImageData](../../debugger/debug-interface-access/idiaimagedata.md)



