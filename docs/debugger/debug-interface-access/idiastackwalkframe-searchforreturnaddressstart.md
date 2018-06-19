---
title: Idiastackwalkframe::searchforreturnaddressstart | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame::searchForReturnAddressStart method
ms.assetid: 47660b9b-6e4f-4dfa-88ab-63dce28f7412
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2581233ceaba4ccf7d4e8593caf7f8b4dd306364
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31463728"
---
# <a name="idiastackwalkframesearchforreturnaddressstart"></a>IDiaStackWalkFrame::searchForReturnAddressStart
Bir dönüş adresi hiç veya neredeyse belirtilen adres için belirtilen yığın çerçevesi arar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
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
 [in] Sanal bellek adresi arama başlayacağı.  
  
 `returnAddress`  
 [out] Yakın işlevi dönüş adresi döndürür `startAddress`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiastackwalkframe](../../debugger/debug-interface-access/idiastackwalkframe.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)