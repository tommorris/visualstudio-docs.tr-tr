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
ms.openlocfilehash: 7ed742971a75d15eccfd6765dbaf242f0afc7890
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)