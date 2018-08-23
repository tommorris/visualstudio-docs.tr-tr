---
title: Idiasymbol::get_timestamp | Microsoft Docs
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
- IDiaSymbol::get_timeStamp method
ms.assetid: 5d707b76-dbaa-4d88-86c3-6f3672cc6d4c
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5df8c81fd21d4130afea9e8263681aeec8cb000
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633301"
---
# <a name="idiasymbolgettimestamp"></a>IDiaSymbol::get_timeStamp
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiasymbol::get_timestamp](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-timestamp).  
  
Temel alınan yürütülebilir dosya zaman damgası alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT get_timeStamp (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Temel alınan yürütülebilir dosyanın zaman damgasını döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
> [!NOTE]
>  Dönüş değeri `S_FALSE` özelliği simge için kullanılabilir değil anlamına gelir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



