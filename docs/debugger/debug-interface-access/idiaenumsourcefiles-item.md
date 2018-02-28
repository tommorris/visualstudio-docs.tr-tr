---
title: Idiaenumsourcefiles::Item | Microsoft Docs
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
- IDiaEnumSourceFiles::Item method
ms.assetid: 3c19d7ed-0232-4b0e-9b10-f33ed9e0c93b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: eef6cc34899d81dec3fac23c3cf350e4f8e5c3de
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiaenumsourcefilesitem"></a>IDiaEnumSourceFiles::Item
Bir kaynak dosya yoluyla bir dizin alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT Item (   
   DWORD            index,  
   IDiaSourceFile** sourceFile  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 dizin  
 [in] Dizin [Idiasourcefile](../../debugger/debug-interface-access/idiasourcefile.md) alınacak nesne. Aralıktaki 0 dizinidir `count`-1, burada `count` tarafından döndürülen [Idiaenumsourcefiles::get_Count](../../debugger/debug-interface-access/idiaenumsourcefiles-get-count.md) yöntemi.  
  
 sourceFile  
 [out] Döndürür bir [Idiasourcefile](../../debugger/debug-interface-access/idiasourcefile.md) istenen kaynak dosyasını temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumsourcefiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)