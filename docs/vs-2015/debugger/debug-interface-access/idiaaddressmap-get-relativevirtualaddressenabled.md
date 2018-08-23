---
title: Idiaaddressmap::get_relativevirtualaddressenabled | Microsoft Docs
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
- IDiaAddressMap::get_relativeVirtualAddressEnabled method
ms.assetid: 4c48af81-7148-4d9a-818e-dbe62cbfc638
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d64f41285c0114d78df4035d11a6d92c714717bd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691445"
---
# <a name="idiaaddressmapgetrelativevirtualaddressenabled"></a>IDiaAddressMap::get_relativeVirtualAddressEnabled
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiaaddressmap::get_relativevirtualaddressenabled](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled).  
  
Göreli sanal adreslerine (RVA) kullanılması ve hesaplama etkin olup olmadığını gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT get_relativeVirtualAddressEnabled (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pRetVal  
 [out] Döndürür `TRUE` RVA hesaplanması etkinse.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Parçaları bir PDB dosyasındaki ilk yüklenmiş olan, RVA etkinleştirilir. RVA kullanımını geçici olarak çağırarak devre dışı bırakılabilir [Idiaaddressmap::put_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md) yöntemi.  
  
 Ayrıca, yeni görüntüyü üstbilgileri çağırarak kurulabilir [Idiaaddressmap::set_imageheaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md) yöntemine bir çağrı tarafından izlenen `put_relativeVirtualAddressEnabled` kullanarak yeni görüntüyü üstbilgileri RVA kullanımını etkinleştirmek için yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaaddressmap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap::set_imageheaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)   
 [IDiaAddressMap::put_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)



