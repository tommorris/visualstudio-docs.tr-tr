---
title: Idiaınjectedsource::get_sourcecompression | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaInjectedSource::get_sourceCompression method
ms.assetid: 854b142f-23a9-466c-bf7f-98e581d5abcd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a56d1eac34c5076be8dbcd7b4e38363a12fe392f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiainjectedsourcegetsourcecompression"></a>IDiaInjectedSource::get_sourceCompression
Kullanılan kaynak sıkıştırma gösterge alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_sourceCompression (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Kullanılan kaynak sıkıştırma göstergesinin döndürür. Sıfır değeri hiçbir kaynak sıkıştırma kullanıldığını belirtir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`. Döndürür `S_FALSE` bu özellik desteklenmiyorsa. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından döndürülen değer kullanılan derleyici özeldir. Örneğin, bir derleyici Çalıştır uzunlukta kodlama veya Huffman stili sıkıştırma kullanabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)