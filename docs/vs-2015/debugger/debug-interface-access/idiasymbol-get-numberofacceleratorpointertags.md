---
title: IDiaSymbol::get_numberOfAcceleratorPointerTags | Microsoft Docs
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
ms.assetid: 1886e3ec-b227-4187-8d93-c5144b4b77ae
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 965991aa2f4b65a369bf051dc008b6dd21b0cfb5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693767"
---
# <a name="idiasymbolgetnumberofacceleratorpointertags"></a>IDiaSymbol::get_numberOfAcceleratorPointerTags
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDiaSymbol::get_numberOfAcceleratorPointerTags](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-numberofacceleratorpointertags).  
  
Hızlandırıcı işaretçi etiket sayısı, bir C++ AMP saplama işlevde döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT get_numberOfAcceleratorPointerTags(   
   DWORD* count);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `count`  
 [out] Bir işaretçi bir `DWORD` Hızlandırıcı sayısı bir C++ AMP saplama işlevde işaretçi etiketleri içeren.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem üzerinde çağrılır bir `IDiaSymbol` karşılık gelen bir C++ AMP Hızlandırıcısı saplama işlevi için arabirim.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



