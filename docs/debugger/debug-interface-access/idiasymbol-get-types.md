---
title: Idiasymbol::get_types | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_types method
ms.assetid: 5f056e0c-e15b-4e00-8f78-aadc8574f7ea
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6521d2a7ffdf5bb285f571e0d3975626f34d84d1
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31470042"
---
# <a name="idiasymbolgettypes"></a>IDiaSymbol::get_types
Bu simgenin derleyici özgü türlerinin dizisini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_types (   
   DWORD       cTypes,  
   DWORD*      pcTypes,  
   IDiaSymbol* types[]  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cTypes`  
 [in] Verileri tutmak için arabellek boyutu.  
  
 `pcTypes`  
 [out] Yazılan türleri sayısını döndürür veya `types` parametresi `NULL`, ardından türleri kullanılabilir toplam sayısı.  
  
 `types[]`  
 [out] İle doldurulması için bir dizi [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md) bu simgenin tüm türleri temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
> [!NOTE]
>  Dönüş değeri `S_FALSE` özelliğin simge için kullanılabilir olup olmadığı anlamına gelir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)