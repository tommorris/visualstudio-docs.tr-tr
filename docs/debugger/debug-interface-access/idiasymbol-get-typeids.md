---
title: Idiasymbol::get_typeıds | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_typeIds method
ms.assetid: 5166e647-fde5-4efe-92bf-77f8ae3fbc9b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 21c0aad37f51ca388c73ada62512887ff67e3e9a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolgettypeids"></a>IDiaSymbol::get_typeIds
Bu simgenin derleyici özel tür tanımlayıcı değerleri alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_typeIds (   
   DWORD  cTypeIds,  
   DWORD* pcTypeIds,  
   DWORD  typeIds[]  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cTypeIds`  
 [in] Verileri tutmak için arabellek boyutu.  
  
 `pcTypeIds`  
 [out] Sayısını döndürür `typeIds` yazılan veya `typeIds` olan `NULL`, ardından türü tanımlayıcıları kullanılabilir toplam sayısı.  
  
 `typeIds[]`  
 [out] Oturum türü tanımlayıcıları doldurulması için bir dizi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
> [!NOTE]
>  Dönüş değeri `S_FALSE` özelliğin simge için kullanılabilir olup olmadığı anlamına gelir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)