---
title: Idialoadcallback2::restrictreferencepathaccess | Microsoft Docs
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
- IDiaLoadCallback2::RestrictReferencePathAccess method
ms.assetid: e20cb45c-0360-4ff0-a92c-b1b6f76d6e85
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3a2ba01723edae02034c90bde32e49c9e4bf5fc6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630207"
---
# <a name="idialoadcallback2restrictreferencepathaccess"></a>IDiaLoadCallback2::RestrictReferencePathAccess
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idialoadcallback2::restrictreferencepathaccess](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idialoadcallback2-restrictreferencepathaccess).  
  
.Exe dosyasının bulunduğu yolu bir .pdb dosyasını ararken izin verilip verilmediğini belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT RestrictReferencePathAccess();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Herhangi bir dışındaki kod dönüş `S_OK` .exe dosyasının bulunduğu bir .pdb dosyası için yol arama önlemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)



