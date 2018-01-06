---
title: "Idiasymbol::get_typeıds | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_typeIds method
ms.assetid: 5166e647-fde5-4efe-92bf-77f8ae3fbc9b
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b186c9f2f8b3ad49808669c1fd04b1fdefe3b82d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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