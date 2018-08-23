---
title: Idiaframedata::get_systemexceptionhandling | Microsoft Docs
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
- IDiaFrameData::get_systemExceptionHandling method
ms.assetid: e8df1972-913c-446c-9779-775575b0caa9
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bf31d69f51e5182d6fb211a0936ba089eb4137ef
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630659"
---
# <a name="idiaframedatagetsystemexceptionhandling"></a>IDiaFrameData::get_systemExceptionHandling
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiaframedata::get_systemexceptionhandling](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaframedata-get-systemexceptionhandling).  
  
Sistem özel durum işleme etkin olup olmadığını gösteren bir bayrak alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT get_systemExceptionHandling (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pRetVal  
 [out] Döndürür `TRUE` sistem özel durum işleme döndürür yürürlükte; Aksi halde ise `FALSE`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`. Döndürür `S_FALSE` varsa bu özelliği desteklenmiyor. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Sistem özel durum işleme, daha sık olarak yapılandırılmış özel durum işleme adı verilir.  
  
 C++ özel durum işleme etkin olup olmadığını belirlemek için çağrı [Idiaframedata::get_cplusplusexceptionhandling](../../debugger/debug-interface-access/idiaframedata-get-cplusplusexceptionhandling.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaframedata](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaFrameData::get_cplusplusExceptionHandling](../../debugger/debug-interface-access/idiaframedata-get-cplusplusexceptionhandling.md)



