---
title: IDiaSymbol::get_acceleratorPointerTags | Microsoft Docs
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
ms.assetid: 30e13cee-e511-49ec-affd-99b0097071b2
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5e4dd78c3b028d1cd20c6a03a2fe072470a2dc1a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697122"
---
# <a name="idiasymbolgetacceleratorpointertags"></a>IDiaSymbol::get_acceleratorPointerTags
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDiaSymbol::get_acceleratorPointerTags](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-acceleratorpointertags).  
  
Bir C++ AMP Hızlandırıcısı saplama işlevi için karşılık gelen tüm Hızlandırıcı işaretçi etiket değerlerini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT get_acceleratorPointerTags(   
   DWORD          cnt,  
   DWORD*         pcnt,  
   DWORD*         pPointerTags);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cnt`  
 [in] Çıkış dizinin boyutu `pPointerTags`.  
  
 `pcnt`  
 [out] C++ AMP Hızlandırıcısı saplama işlevi Hızlandırıcı işaretçi etiketleri sayısı.  
  
 `pPointerTags`  
 [out] A `DWORD` C++ AMP Hızlandırıcısı saplama işlevi Hızlandırıcı işaretçi etiketi değerler ile doldurulan bir dizi işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem üzerinde çağrılır bir `IDiaSymbol` karşılık gelen bir C++ AMP Hızlandırıcısı saplama işlevi için arabirim.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



