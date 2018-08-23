---
title: Idiasectioncontrib::get_read | Microsoft Docs
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
- IDiaSectionContrib::get_read method
ms.assetid: 68bfb35c-eabd-412a-bc8f-3094703b98c4
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 611a3ada78448f431864591d8649bace32bf2318
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629759"
---
# <a name="idiasectioncontribgetread"></a>IDiaSectionContrib::get_read
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiasectioncontrib::get_read](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasectioncontrib-get-read).  
  
Bölüm okunup okunamayacağını gösteren bir bayrak alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT get_read (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Döndürür `TRUE` bölümü okunabiliyorsa; Aksi halde döndürür `FALSE`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`. Döndürür `S_FALSE` varsa bu özelliği desteklenmiyor. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)



