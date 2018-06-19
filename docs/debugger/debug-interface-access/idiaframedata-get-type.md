---
title: Idiaframedata::get_type | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_type method
ms.assetid: efca38b5-c479-4d0a-a164-f903f25c5509
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5b95262fb5cc9afce25e9f4120b981543939e5be
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31460446"
---
# <a name="idiaframedatagettype"></a>IDiaFrameData::get_type
Derleyici özgü çerçeve türünü alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_type (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Arasında bir değer döndürür [StackFrameTypeEnum numaralandırması](../../debugger/debug-interface-access/stackframetypeenum.md) derleyici özgü çerçeve türünü gösteren numaralandırma.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`. Döndürür `S_FALSE` bu özellik desteklenmiyorsa. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaframedata](../../debugger/debug-interface-access/idiaframedata.md)   
 [StackFrameTypeEnum numaralandırması](../../debugger/debug-interface-access/stackframetypeenum.md)