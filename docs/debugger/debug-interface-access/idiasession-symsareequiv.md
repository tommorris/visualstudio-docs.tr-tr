---
title: Idiasession::symsareequiv | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::symsAreEquiv method
ms.assetid: 9941d520-e203-46c0-83c3-b3a967f4fc59
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cc92a38305e7cc8c74b4ada0d560b314ed92da8f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31460049"
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