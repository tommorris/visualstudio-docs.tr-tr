---
title: Idiastackwalkframe::put_registervalue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame::put_registerValue method
ms.assetid: 2d8b79b6-7240-43fe-b24e-e4ff3e2c15b0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 596cadedce3d33bb9cc0ccb26421a3244d19cadc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiastackwalkframeputregistervalue"></a>IDiaStackWalkFrame::put_registerValue
Bir kayıt değerini ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT put_registerValue (   
   DWORD     index,  
   ULONGLONG NewVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `index`  
 [in] Arasında bir değer [CV_HREG_e numaralandırması](../../debugger/debug-interface-access/cv-hreg-e.md) yazmak için Kaydet'i belirtme numaralandırması.  
  
 `NewVal`  
 [in] Yeni değer kaydedin.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiastackwalkframe](../../debugger/debug-interface-access/idiastackwalkframe.md)   
 [CV_HREG_e numaralandırması](../../debugger/debug-interface-access/cv-hreg-e.md)