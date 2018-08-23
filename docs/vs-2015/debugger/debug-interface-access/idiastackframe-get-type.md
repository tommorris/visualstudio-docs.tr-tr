---
title: Idiastackframe::get_type | Microsoft Docs
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
- IDiaStackFrame::get_type method
ms.assetid: 99daa97b-5c05-455d-bd1e-800762ccf7c9
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b0f1e9ddc0a556cfbff4a04fcaf856176297e426
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684557"
---
# <a name="idiastackframegettype"></a>IDiaStackFrame::get_type
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiastackframe::get_type](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackframe-get-type).  
  
Çerçeve türünü alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT get_type (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Bir değer döndürür [StackFrameTypeEnum numaralandırması](../../debugger/debug-interface-access/stackframetypeenum.md) sabit listesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`. Döndürür `S_FALSE` özelliği desteklenmiyorsa. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiastackframe](../../debugger/debug-interface-access/idiastackframe.md)   
 [StackFrameTypeEnum numaralandırması](../../debugger/debug-interface-access/stackframetypeenum.md)



