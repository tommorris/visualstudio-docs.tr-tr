---
title: Idialoadcallback::notifyopenpdb | Microsoft Docs
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
- IDiaLoadCallback::NotifyOpenPDB method
ms.assetid: c0547f99-8468-4e57-82ca-9ef7d6707c8a
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a0e0013ff74376bd9f91ada16d8205d0bb860afd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628738"
---
# <a name="idialoadcallbacknotifyopenpdb"></a>IDiaLoadCallback::NotifyOpenPDB
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idialoadcallback::notifyopenpdb](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idialoadcallback-notifyopenpdb).  
  
Bir aday .pdb dosyası açıldığında çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT NotifyOpenPDB (   
   LPCOLESTR pdbPath,  
   HRESULT   resultCode  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pdbPath`  
 [in] .Pdb dosyasının tam yolu.  
  
 `resultCode`  
 [in] Başarıyı gösteren kod (`S_OK`) veya bu dosyaya uygulanan yük hatası.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Dönüş kodu genellikle göz ardı edilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)



