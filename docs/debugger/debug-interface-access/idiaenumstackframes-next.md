---
title: Idiaenumstackframes::Next | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumStackFrames::Next method
ms.assetid: 09378a21-d5e3-4213-b7e2-10f04d85295f
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 784744321a76c7142c948bac5c5f83a896d443be
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumstackframesnext"></a>IDiaEnumStackFrames::Next
Belirtilen sayıda yığın çerçeve öğeyi numaralandırma dizisini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT Next(   
   ULONG             celt,  
   IDiaStackFrame**  rgelt,  
   ULONG*            pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 celt  
 [in] Alınacak Numaralandırıcı stackframe öğe sayısı.  
  
 rgelt  
 [out] İstenen ile doldurulması için bir dizi [Idiastackframe](../../debugger/debug-interface-access/idiastackframe.md) nesneleri.  
  
 pceltFetched  
 [out] Yığın sayısı çerçeve öğeleri getirilen Numaralandırıcı döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`. Döndürür `S_FALSE` olması durumunda daha fazla yığın çerçeve yok. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumstackframes](../../debugger/debug-interface-access/idiaenumstackframes.md)   
 [Idiastackframe](../../debugger/debug-interface-access/idiastackframe.md)