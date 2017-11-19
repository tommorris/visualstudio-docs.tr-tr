---
title: Idiaenumframedata::framebyrva | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumFrameData::frameByRVA method
ms.assetid: 4b8dec05-e76c-4cc4-9644-2369d583849f
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6b6af518b68c8e9384ff701305bce9253eedac56
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumframedataframebyrva"></a>IDiaEnumFrameData::frameByRVA
Bir çerçeve göreli sanal adresiyle (RAV) döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT frameByRVA(   
   DWORD           relativeVirtualAddress,  
   IDiaFrameData** frame  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 relativeVirtualAddress  
 [in] Çerçevenin ilgilendiğiniz RVA.  
  
 çerçeve  
 [out] Döndürür bir [Idiaframedata](../../debugger/debug-interface-access/idiaframedata.md) sağlanan adresi içeren çerçeveyi temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`. Döndürür `S_FALSE` belirtilen adresi çerçeve veri eşleşmesi durumunda. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumframedata](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [Idiaframedata](../../debugger/debug-interface-access/idiaframedata.md)