---
title: Idialinenumber::get_addresssection | Microsoft Docs
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
- IDiaLineNumber::get_addressSection method
ms.assetid: a01c1bae-04b2-4c30-8621-60939a3124c2
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2874e0497c2558be881eb9118561598855e21d3a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630334"
---
# <a name="idialinenumbergetaddresssection"></a>IDiaLineNumber::get_addressSection
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idialinenumber::get_addresssection](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idialinenumber-get-addresssection).  
  
Bir blok başladığı bellek adresi bölüm parçası alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT get_addressSection (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pRetVal  
 [out] Bir blok başladığı bellek adresi bölüm bölümünü döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`. Döndürür `S_FALSE` varsa bu özelliği desteklenmiyor. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="example"></a>Örnek  
  
```cpp#  
CComPtr< IDiaLineNumber > pLine;  
DWORD seg;  
pLine->get_addressSection( &seg );  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idialinenumber](../../debugger/debug-interface-access/idialinenumber.md)   
 [IDiaLineNumber::get_addressOffset](../../debugger/debug-interface-access/idialinenumber-get-addressoffset.md)



