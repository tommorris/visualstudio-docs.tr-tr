---
title: Idiaframedata::get_cplusplusexceptionhandling | Microsoft Docs
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
- IDiaFrameData::get_cplusplusExceptionHandling method
ms.assetid: 54ee9cde-ce8e-45f1-809c-6fbad800d850
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c41bf1371f2ee2521c489787b5a566f012ae0dd1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697477"
---
# <a name="idiaframedatagetcplusplusexceptionhandling"></a>IDiaFrameData::get_cplusplusExceptionHandling
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiaframedata::get_cplusplusexceptionhandling](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaframedata-get-cplusplusexceptionhandling).  
  
C++ özel durum işleme etkin olup olmadığını gösteren bir bayrak alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT get_cplusplusExceptionHandling (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Döndürür `TRUE` C++ özel durum işleme döndürür yürürlükte; Aksi halde ise `FALSE`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`. Döndürür `S_FALSE` varsa bu özelliği desteklenmiyor. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Yapılandırılmış özel durum belirlemek için işleme (C++ özel durum işleme gelen çok farklı olmayan) etkindir, çağrı [Idiaframedata::get_systemexceptionhandling](../../debugger/debug-interface-access/idiaframedata-get-systemexceptionhandling.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaframedata](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaFrameData::get_systemExceptionHandling](../../debugger/debug-interface-access/idiaframedata-get-systemexceptionhandling.md)



