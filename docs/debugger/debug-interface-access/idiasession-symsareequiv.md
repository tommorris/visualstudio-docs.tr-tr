---
title: Idiasession::symsareequiv | Microsoft Docs
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
- IDiaSession::symsAreEquiv method
ms.assetid: 9941d520-e203-46c0-83c3-b3a967f4fc59
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 550218c2d0c2206cdfe417b0e8faff978f9a21e5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasessionsymsareequiv"></a>IDiaSession::symsAreEquiv
İki simge eşdeğer olup olmadığını denetler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT symsAreEquiv (   
   IDiaSymbol* symbolA,  
   IDiaSymbol* symbolB  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `symbolA`  
 [in] İlk [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md) Karşılaştırmada kullanılan nesne.  
  
 `symbolB`  
 [in] İkinci `IDiaSymbol` Karşılaştırmada kullanılan nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Simgeler eşdeğer olup olmadığını döndürür `S_OK`; Aksi takdirde döndürür `S_FALSE`, simgeler eşdeğer değildir. Aksi takdirde bir hata kodunu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)