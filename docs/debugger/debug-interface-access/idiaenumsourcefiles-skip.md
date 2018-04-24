---
title: Idiaenumsourcefiles::Skip | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSourceFiles::Skip method
ms.assetid: 4821e6dd-d33f-403d-857d-e3ae81e4a9e3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3dedc9e3218d56c4e58f35c70b3bce8bf4dd8ae7
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaenumsourcefilesskip"></a>IDiaEnumSourceFiles::Skip
Belirtilen sayıda kaynak dosyalarında bir numaralandırma sırasını atlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT Skip (   
   ULONG celt  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 celt  
 [in] Kaynak dosyaları atlamayı numaralandırması dizisindeki sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` atlamak için daha fazla kaynak dosya yoksa.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)