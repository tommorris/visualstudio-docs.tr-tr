---
title: Idiastackwalkframe::searchforreturnaddressstart | Microsoft Docs
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
- IDiaStackWalkFrame::searchForReturnAddressStart method
ms.assetid: 47660b9b-6e4f-4dfa-88ab-63dce28f7412
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ef077fcea728f8440ca07ae316fdc87ea5b88089
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684363"
---
# <a name="idiastackwalkframesearchforreturnaddressstart"></a>IDiaStackWalkFrame::searchForReturnAddressStart
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiastackwalkframe::searchforreturnaddressstart](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddressstart).  
  
Belirtilen yığın çerçevesinin veya belirtilen adres'e yakın bir dönüş adresi arar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT searchForReturnAddressStart (   
   IDiaFrameData* frame,  
   ULONGLONG      startAddress,  
   ULONGLONG*     returnAddress  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `frame`  
 [in] Bir [Idiaframedata](../../debugger/debug-interface-access/idiaframedata.md) geçerli yığın çerçevesini temsil eden nesne.  
  
 `startAddress`  
 [in] Bir sanal bellek adres aramaya başlanacak.  
  
 `returnAddress`  
 [out] En yakın işlevi dönüş adresi döndürür `startAddress`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiastackwalkframe](../../debugger/debug-interface-access/idiastackwalkframe.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)



