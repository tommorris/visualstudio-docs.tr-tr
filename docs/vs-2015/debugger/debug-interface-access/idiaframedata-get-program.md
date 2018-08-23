---
title: Idiaframedata::get_program | Microsoft Docs
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
- IDiaFrameData::get_program method
ms.assetid: 9201409e-b4b1-4e2e-a9f8-d17678ac538b
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6daf5262552d056a6ac2d46a092fe94ec7510b15
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695872"
---
# <a name="idiaframedatagetprogram"></a>IDiaFrameData::get_program
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiaframedata::get_program](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaframedata-get-program).  
  
Geçerli işlevi çağırmadan önce ayarlanmış kayıt hesaplamak için kullanılan program dizesini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT get_program (   
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Program dizeyi döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`. Döndürür `S_FALSE` varsa bu özelliği desteklenmiyor. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Program dize prolog kurulabilmesi yorumlanır makroları dizisidir. Örneğin, tipik bir yığın çerçevesi program dize kullanabilirsiniz `"$T0 $ebp = $eip $T0 4 + ^ = $ebp $T0 ^ = $esp $T0 8 + ="`. Burada işleçler işlenenlerin izleyin, ters Lehçe gösterimi biçimidir. `T0` geçici bir değişkende temsil eder. Bu örnek, aşağıdaki adımları gerçekleştirir:  
  
1.  Kaydının içeriğini taşımak `ebp` için `T0`.  
  
2.  Ekleme `4` değerine `T0` bir adresi üretmek, adresten değeri Al ve kayıttaki değeri depolamak için `eip`.  
  
3.  Depolanan adresinden değer elde `T0` ve kayıttaki değeri depola `ebp`.  
  
4.  Ekleme `8` değerine `T0` ve kayıttaki değeri depola `esp`.  
  
 Program dize CPU ve geçerli yığın çerçevesi tarafından temsil edilen işlev için ayarlanan çağırma kuralı için özel olduğunu unutmayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)



