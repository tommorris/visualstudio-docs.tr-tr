---
title: IDiaSymbol::get_acceleratorPointerTags | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 30e13cee-e511-49ec-affd-99b0097071b2
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e8467c25c8665dfb3fc91ea29d9b99c184b7ecce
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolgetacceleratorpointertags"></a>IDiaSymbol::get_acceleratorPointerTags
Karşılık gelen tüm Hızlandırıcı işaretçi etiket değerleri bir C++ AMP Hızlandırıcı saplama işlevi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_acceleratorPointerTags(   
   DWORD          cnt,  
   DWORD*         pcnt,  
   DWORD*         pPointerTags);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cnt`  
 [in] Çıkış dizisi boyutunu `pPointerTags`.  
  
 `pcnt`  
 [out] Hızlandırıcı işaretçi C++ AMP Hızlandırıcı saplama işlevi etiketlerinde sayısı.  
  
 `pPointerTags`  
 [out] A `DWORD` C++ AMP Hızlandırıcı saplama işlevi Hızlandırıcı işaretçi etiketi değerler ile doldurulan bir dizi işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem üzerinde çağrılır bir `IDiaSymbol` C++ AMP Hızlandırıcı saplama işleve karşılık gelen arabirim.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)