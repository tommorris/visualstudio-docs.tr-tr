---
title: IDiaSymbol::get_restrictedType | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c48b00a6-26b0-47b0-b824-fe44dedbc756
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 405dbeb5354a1f7d04ab22ef87f5b026c08867e9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetrestrictedtype"></a>IDiaSymbol::get_restrictedType
Belirtir olup olmadığını `this` işaretçi bayrak olarak kısıtlı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_restrictedType(   
   BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Bir işaretçi bir `BOOL` belirtir olup olmadığını `this` işaretçi bayrak olarak kısıtlı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)