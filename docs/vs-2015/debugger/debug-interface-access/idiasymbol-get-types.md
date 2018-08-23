---
title: Idiasymbol::get_types | Microsoft Docs
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
- IDiaSymbol::get_types method
ms.assetid: 5f056e0c-e15b-4e00-8f78-aadc8574f7ea
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 78be235d82e0bf9113bcfdcef0bf85575e5f5d35
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683794"
---
# <a name="idiasymbolgettypes"></a>IDiaSymbol::get_types
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiasymbol::get_types](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-types).  
  
Derleyici özel türleri için bu simge dizisini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 [out] Yazılan türleri sayısı döndürür veya `types` parametresi `NULL`, ardından kullanılabilir türleri toplam sayısı.  
  
 `types[]`  
 [out] İle doldurulacak bir dizi [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md) bu simgenin tüm türleri temsil eden nesneleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
> [!NOTE]
>  Dönüş değeri `S_FALSE` özelliği simge için kullanılabilir değil anlamına gelir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



