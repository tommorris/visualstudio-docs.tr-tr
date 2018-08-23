---
title: Idiastackframe::get_registervalue | Microsoft Docs
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
- IDiaStackFrame::get_registerValue method
ms.assetid: cbe3d8ac-319a-40ac-bc3e-4eb81b2d7807
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 496d15d8bfed0fc6d674e09a2bc9046788e11ca1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692677"
---
# <a name="idiastackframegetregistervalue"></a>IDiaStackFrame::get_registerValue
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiastackframe::get_registervalue](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackframe-get-registervalue).  
  
Yığın çerçevesi içinde depolanmış olarak belirtilen bir kayıt değeri alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT get_registerValue(  
   ULONG      registerIndex,  
   ULONGLONG *pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `registerIndex`  
 [in] Aşağıdakilerden birini [CV_HREG_e numaralandırması](../../debugger/debug-interface-access/cv-hreg-e.md) sabit listesi değerleri.  
  
 `pRetVal`  
 [out] Kayıt defterinde depolanan değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi halde hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiastackframe](../../debugger/debug-interface-access/idiastackframe.md)   
 [CV_HREG_e numaralandırması](../../debugger/debug-interface-access/cv-hreg-e.md)



