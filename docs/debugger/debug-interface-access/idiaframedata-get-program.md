---
title: Idiaframedata::get_program | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_program method
ms.assetid: 9201409e-b4b1-4e2e-a9f8-d17678ac538b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dc770db5f5cf16d9870e05ada01e235206b94078
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiaframedatagetprogram"></a>IDiaFrameData::get_program
Geçerli işlevi çağırmadan önce ayarlayın kayıt hesaplamak için kullanılan program dizesini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_program (   
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Program dize döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`. Döndürür `S_FALSE` bu özellik desteklenmiyorsa. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Program dize giriş kurabilmek için yorumlanan makroları dizisidir. Örneğin, tipik yığın çerçevesi program dizesi kullanabilir `"$T0 $ebp = $eip $T0 4 + ^ = $ebp $T0 ^ = $esp $T0 8 + ="`. Biçim burada işleçleri işlenenler izleyin ters Lehçe gösterimidir. `T0` Yığında geçici bir değişkeni temsil eder. Bu örnekte aşağıdaki adımları gerçekleştirir:  
  
1.  YAZMAÇ içeriğini taşımak `ebp` için `T0`.  
  
2.  Ekleme `4` değerine `T0` bir adresi oluşturmak, o adresinden değerini almak ve kayıttaki değeri depolamak için `eip`.  
  
3.  Depolanan adresinden değeri Al `T0` ve değeri kayıttaki depola `ebp`.  
  
4.  Ekleme `8` değerine `T0` ve değeri kayıttaki depola `esp`.  
  
 Program dize CPU ve geçerli yığın çerçevesi tarafından temsil edilen işlevi için ayarlanan çağırma belirli olduğuna dikkat edin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)