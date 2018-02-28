---
title: Idialoadcallback2::restrictoriginalpathaccess | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback2::RestrictOriginalPathAccess method
ms.assetid: 31fde3af-2824-4b0f-8d0d-cee6046596f6
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 84c9eabb3eaeaec29e790a12c802aae5b1cfb610
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idialoadcallback2restrictoriginalpathaccess"></a>IDiaLoadCallback2::RestrictOriginalPathAccess
.Pdb dosyasını özgün hata ayıklama dizinde aramak uygun olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT RestrictOriginalPathAccess ();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Herhangi bir başka dönüş kodu `S_OK` özgün hata ayıklama dizinindeki .pdb dosyasını arayan engeller. Özgün hata ayıklama yürütülebilir dosyada hata ayıklama açıldığında derlenmiş simge dosyasının yolu dizindir. Bu yol mutlaka yürütülebilir dosyanın bulunduğu yolu ile aynı değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)