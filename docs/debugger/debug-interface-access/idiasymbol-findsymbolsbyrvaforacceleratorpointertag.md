---
title: IDiaSymbol::findSymbolsByRVAForAcceleratorPointerTag | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 024ccd78-5867-4ca7-bc26-548758e9ac53
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7e42ce2113ed578802074714beac2e317786619b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolfindsymbolsbyrvaforacceleratorpointertag"></a>IDiaSymbol::findSymbolsByRVAForAcceleratorPointerTag
Bu yöntem karşılık gelen bir etiket değeri verildiğinde, bu saplama işlevinde, belirtilen bir göreli sanal adreste bulunan sembolleri numaralandırması döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT findSymbolsByRVAForAcceleratorPointerTag (   
   DWORD             tagValue,  
   DWORD             rva,  
   IDiaEnumSymbols** ppResult);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `tagValue`  
 [in] İşaretçi etiket değeri pointee simgesi kayıtları bulunamadı.  
  
 `rva`  
 [in] Belirtilen etiket değeri pointee değişkenle karşılık simgeleri filtrelemede kullanılan rva.  
  
 `ppResult`  
 [out] Bir işaretçi bir `IDiaEnumSymbols` sonucu ile başlatılmış arabirim işaretçisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem yalnızca çağrısı bir `IDiaSymbol` bir Hızlandırıcı saplama işleve karşılık gelen arabirim.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)