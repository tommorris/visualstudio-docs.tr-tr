---
title: Idialoadcallback2::restrictdbgaccess | Microsoft Docs
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
- IDiaLoadCallback2::RestrictDBGAccess method
ms.assetid: 63b67a93-2910-4fff-aa70-6b2eaa08e5c8
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d30ab4d2c64eea3b607a582848fcd2bfbcf88819
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630320"
---
# <a name="idialoadcallback2restrictdbgaccess"></a>IDiaLoadCallback2::RestrictDBGAccess
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idialoadcallback2::restrictdbgaccess](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idialoadcallback2-restrictdbgaccess).  
  
Hata ayıklama ile ilgili bilgi arayan .dbg dosyaları izin verilip verilmediğini belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT RestrictDBGAccess();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Herhangi bir başka değer dönüş `S_OK` hata ayıklama bilgileri .dbg dosyaları aranıyor önlemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)



