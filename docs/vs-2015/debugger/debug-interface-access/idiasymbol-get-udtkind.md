---
title: Idiasymbol::get_udtkind | Microsoft Docs
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
- IDiaSymbol::get_udtKind method
ms.assetid: 4002f887-aea6-4475-b302-67c57079fe0a
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a0a47dea769f4a11977eae5fa53cd503d16819e8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628955"
---
# <a name="idiasymbolgetudtkind"></a>IDiaSymbol::get_udtKind
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiasymbol::get_udtkind](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-udtkind).  
  
Bir kullanıcı tanımlı tür (UDT) çeşitli alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT get_udtKind (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Bir değer döndürür [UdtKind numaralandırması](../../debugger/debug-interface-access/udtkind.md) bir UDT türünü belirten sabit listesi: yapısı, sınıf veya birleşim.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya hata kodu.  
  
> [!NOTE]
>  Dönüş değeri `S_FALSE` özelliği simge için kullanılabilir değil anlamına gelir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [UdtKind numaralandırması](../../debugger/debug-interface-access/udtkind.md)



