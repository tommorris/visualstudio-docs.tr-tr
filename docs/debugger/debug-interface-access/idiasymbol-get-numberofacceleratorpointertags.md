---
title: IDiaSymbol::get_numberOfAcceleratorPointerTags | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 1886e3ec-b227-4187-8d93-c5144b4b77ae
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7701fefc0c9d754d4d1728b5713deb9e21428a5f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetnumberofacceleratorpointertags"></a>IDiaSymbol::get_numberOfAcceleratorPointerTags
Hızlandırıcı işaretçi etiket sayısı C++ AMP saplama işlevinde döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_numberOfAcceleratorPointerTags(   
   DWORD* count);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `count`  
 [out] Bir işaretçi bir `DWORD` bir C++ AMP saplama işlev işaretçisi etiketleri Hızlandırıcı sayısı tutan.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem üzerinde çağrılır bir `IDiaSymbol` C++ AMP Hızlandırıcı saplama işleve karşılık gelen arabirim.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)