---
title: Idiaenumsectioncontribs::Skip | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSectionContribs::Skip method
ms.assetid: 7471a178-5134-41b2-80a6-51ff96abe916
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b089309fbbee5f0b4b607c97658721bdc276ce41
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaenumsectioncontribsskip"></a>IDiaEnumSectionContribs::Skip
Belirtilen sayıda bölüm katkı bir numaralandırma sırasını atlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT Skip(   
   ULONG celt  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `celt`  
 [in] Bölüm Katkıları atlamak için numaralandırma dizisindeki sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` atlamak için daha fazla bölüm katkı varsa.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)