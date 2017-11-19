---
title: Idiaaddressmap::put_imagealign | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaAddressMap::put_imageAlign method
ms.assetid: f9ce875d-c263-43e5-a534-f34c37f9866f
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 38856520641ff2ea191e3f712a1f355e841e1aff
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaaddressmapputimagealign"></a>IDiaAddressMap::put_imageAlign
Resmi hizalaması ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT put_imageAlign (   
   DWORD NewVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 NewVal  
 [in] Görüntü hizalama için yeni değer çalıştırılabilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Görüntüleri (yüklenen yürütülebilir dosyalar) için belirtilen bellek sınırlarını hizalanır. Bu hizalama, geçerli sistem mimarisi ve derleme ve bağlama zamanı seçenekleri tarafından etkilenebilir. Her zaman resmi hizalaması bayt sınırları ' dir. Aşağıdaki görüntü hizalama değerler geçerlidir: 1, 2, 4, 8, 16, 32 ve 64 baytlık sınırlar.  
  
 Geçerli resmi hizalaması çağrısıyla alınabilir [Idiaaddressmap::get_imagealign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md) yöntemi.  
  
> [!NOTE]
>  Görüntü zaten bu yöntemi çağrılabilir zamanına göre yüklenir. `put_imageAlign` Yöntemi genelde kullanılan görüntü taşınmış veya değiştirilmiş ve yeni bir hizalama gereklidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaaddressmap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap::get_imagealign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)