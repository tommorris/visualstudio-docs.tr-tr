---
title: Idiastackwalkhelper::imageforva | Microsoft Docs
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
- IDiaStackWalkHelper::imageForVA method
ms.assetid: 8d4edabf-3c01-4fef-8b61-4779f3371067
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1a67d092f811f621fe0cffa890c2455f3385f98c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42678867"
---
# <a name="idiastackwalkhelperimageforva"></a>IDiaStackWalkHelper::imageForVA
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiastackwalkhelper::imageforva](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackwalkhelper-imageforva).  
  
Bellek bir sanal adres yere yürütülebilir dosyası bellek alanında belirtilen bir yürütülebilir dosyası görüntü başlangıcını döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT imageForVA(  
   ULONGLONG  vaContext,  
   ULONGLONG *pvaImageStart  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `vaContext`  
 [in] Yere yürütülebilir dosyası alanda bulunan sanal adres.  
  
 `pvaImageStart`  
 [out] Yürütülebilir dosyası görüntüsünün sanal başlangıç adresini döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)



