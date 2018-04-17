---
title: Idiasourcefile::get_checksumtype | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile::get_checksumType method
ms.assetid: 4c363e61-a6a9-409a-9cc0-d06eb2bee645
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d372ad37419d95647a1492503a0b6cabe70ba649
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiasourcefilegetchecksumtype"></a>IDiaSourceFile::get_checksumType
Sağlama türünü alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_checksumType (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Sağlama türü döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Sağlama türü için bir sağlama toplamı algoritması eşlenmiş bir değerdir. Örneğin, standart PDB dosya biçimi genellikle şu değerlerden biri olabilir:  
  
|Sağlama türü|CryptoAPI etiketi|Açıklama|  
|-------------------|---------------------|-----------------|  
|0|\<yok >|Kullanılabilir sağlama mevcut.|  
|1.|`CALG_MD5`|MD5 karma algoritması ile oluşturulan bir sağlama toplamı.|  
|2|`CALG_SHA1`|SHA1 karma algoritması ile oluşturulan bir sağlama toplamı.|  
  
 `CryptoAPI` Etiketleri olan `ALG_ID` numaralandırması. Karma algoritmaları ile ilgili daha fazla bilgi için başvurun `CryptoAPI` Microsoft bölümünü [!INCLUDE[winsdkshort](../../debugger/debug-interface-access/includes/winsdkshort_md.md)].  
  
 Kaynak dosya için asıl sağlama toplamı bayt elde etmek için arama [Idiasourcefile::get_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasourcefile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSourceFile::get_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md)