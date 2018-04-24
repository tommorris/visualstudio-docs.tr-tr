---
title: Idiaframedata::get_lengthprolog | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_lengthProlog method
ms.assetid: 5f042ff1-e74e-430a-be34-d2cf1b18eff2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8033e0f769c0222dc8c3ee90d680ea6f2de279fa
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaframedatagetlengthprolog"></a>IDiaFrameData::get_lengthProlog
Başlangıç kod bloğundaki bayt sayısını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_lengthProlog (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Başlangıç kodu bayt sayısını döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`. Döndürür `S_FALSE` bu özellik desteklenmiyorsa. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Başlangıç kodu kayıtlarını saklayan, CPU durumunu ayarlar ve işlev için yığın kurar yönergeler dizisidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)