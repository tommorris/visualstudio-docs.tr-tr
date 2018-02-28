---
title: IDiaSymbol::get_isAcceleratorStubFunction | Microsoft Docs
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
ms.assetid: cc4ea375-76f6-4ba8-baed-c5fa82108137
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5f95f46037045a6d88747c137a5130851d3ed9e9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetisacceleratorstubfunction"></a>IDiaSymbol::get_isAcceleratorStubFunction
Simgenin bir üst düzey işlevi simge karşılık gelen bir Hızlandırıcı için derlenmiş bir gölgelendirici için karşılık gelen olup olmadığını gösterir bir `parallel_for_each` çağırın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_isAcceleratorStubFunction(   
   BOOL* pFlag);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pFlag`  
 [out] Bir işaretçi bir `BOOL` simgenin bir üst düzey işlevi simge karşılık gelen bir Hızlandırıcı için derlenmiş bir gölgelendirici için karşılık gelen olup olmadığını bildiren bir `parallel_for_each` çağırın.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)