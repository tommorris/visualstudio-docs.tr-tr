---
title: IDiaSymbol::get_isAcceleratorStubFunction | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cc4ea375-76f6-4ba8-baed-c5fa82108137
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 75e9e55165d4ba385379950a4f33fec65180b23d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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