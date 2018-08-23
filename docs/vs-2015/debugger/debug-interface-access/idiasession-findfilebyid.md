---
title: Idiasession::findfilebyıd | Microsoft Docs
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
- IDiaSession::findFileById method
ms.assetid: 710efe04-78b5-4f3e-a1d8-f9b069063503
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e54267e86854098e263c74a9d0e7042540e02025
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695123"
---
# <a name="idiasessionfindfilebyid"></a>IDiaSession::findFileById
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiasession::findfilebyıd](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasession-findfilebyid).  
  
Bir kaynak dosyası, kaynak dosya tanımlayıcısı tarafından alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT findFileById (   
   DWORD            uniqueId,  
   IDiaSourceFile** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `uniqueId`  
 [in] Kaynak dosya tanımlayıcısını belirtir.  
  
 `ppResult`  
 [out] Döndürür bir [Idiasourcefile](../../debugger/debug-interface-access/idiasourcefile.md) kaynak dosyasını temsil eden bir nesne alındı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Kaynak dosya tanımlayıcısı, dahili olarak DIA SDK, tüm kaynak dosyaları benzersiz hale getirmek için kullanılan benzersiz bir değerdir. Bu yöntem genellikle DIA SDK'SININ dahili olarak kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasession::findfile](../../debugger/debug-interface-access/idiasession-findfile.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)



