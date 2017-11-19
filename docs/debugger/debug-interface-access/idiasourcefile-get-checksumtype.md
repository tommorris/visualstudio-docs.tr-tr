---
title: Idiasourcefile::get_checksumtype | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSourceFile::get_checksumType method
ms.assetid: 4c363e61-a6a9-409a-9cc0-d06eb2bee645
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8fafd9e813c22b899603a2e62c5a2c90ece1a709
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Idiasourcefile::get_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md)