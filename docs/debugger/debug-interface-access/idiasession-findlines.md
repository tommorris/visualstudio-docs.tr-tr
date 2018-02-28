---
title: Idiasession::findlines | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findLines method
ms.assetid: d6e84916-fd55-457e-b057-57f97b51fe73
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c1edb84e30861f269fb8658d95b0e404178d9662
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasessionfindlines"></a>IDiaSession::findLines
Satır numaraları belirtilen derlenecek ve kaynak dosya tanımlayıcıları içinde alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT findLines (   
   IDiaSymbol*           compiland,  
   IDiaSourceFile*       file,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `compiland`  
 [in] Bir [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md) derlenecek temsil eden nesne. Bu arabirim için satır numaralarını arama yapılacak bir bağlamda olarak kullanın.  
  
 `file`  
 [in] Bir [Idiasourcefile](../../debugger/debug-interface-access/idiasourcefile.md) içinde satır numaraları için arama yapmak istediğiniz kaynak dosyasını temsil eden nesne.  
  
 `ppResult`  
 [out] Döndürür bir [Idiaenumlinenumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) satır numaralarını listesini içeren nesne alındı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumlinenumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasourcefile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)