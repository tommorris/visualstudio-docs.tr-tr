---
title: Idiasourcefile::get_checksumtype | Microsoft Docs
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
- IDiaSourceFile::get_checksumType method
ms.assetid: 4c363e61-a6a9-409a-9cc0-d06eb2bee645
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd51a553cab29ac7741eaa91ada356897551e12a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686392"
---
# <a name="idiasourcefilegetchecksumtype"></a>IDiaSourceFile::get_checksumType
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiasourcefile::get_checksumtype](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasourcefile-get-checksumtype).  
  
Sağlama türünü alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT get_checksumType (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Sağlama türünü döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Sağlama toplamı, bir sağlama toplamı algoritması için eşlenmiş bir değer türüdür. Örneğin, standart PDB dosya biçimine genellikle aşağıdaki değerlerden biri olabilir:  
  
|Sağlama türü|CryptoAPI etiketi|Açıklama|  
|-------------------|---------------------|-----------------|  
|0|\<yok >|Sağlama mevcut.|  
|1.|`CALG_MD5`|bir MD5 karma algoritması ile oluşturulan bir sağlama toplamı.|  
|2|`CALG_SHA1`|SHA1 karma algoritması ile oluşturulan bir sağlama toplamı.|  
  
 `CryptoAPI` Olan etiketleri `ALG_ID` sabit listesi. Karma algoritmaları hakkında daha fazla bilgi için `CryptoAPI` Microsoft bölümünü [!INCLUDE[winsdkshort](../../includes/winsdkshort-md.md)].  
  
 Kaynak dosyası için asıl sağlama toplamı bayt elde etmek için çağrı [Idiasourcefile::get_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasourcefile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSourceFile::get_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md)



