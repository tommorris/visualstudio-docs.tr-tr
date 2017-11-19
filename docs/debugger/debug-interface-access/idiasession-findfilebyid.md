---
title: "Idiasession::findfilebyıd | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSession::findFileById method
ms.assetid: 710efe04-78b5-4f3e-a1d8-f9b069063503
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1996bed14323adeac794f12ed4307e96e3ba8b54
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasessionfindfilebyid"></a>IDiaSession::findFileById
Bir kaynak dosya kaynak dosya tanımlayıcısı tarafından alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT findFileById (   
   DWORD            uniqueId,  
   IDiaSourceFile** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `uniqueId`  
 [in] Kaynak dosya tanımlayıcısını belirtir.  
  
 `ppResult`  
 [out] Döndürür bir [Idiasourcefile](../../debugger/debug-interface-access/idiasourcefile.md) kaynak dosyasını temsil eden nesnesi alınamadı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Kaynak dosya tanımlayıcısı DIA SDK tüm kaynak dosyaları benzersiz hale getirmek için dahili olarak kullanılan benzersiz bir değerdir. Bu yöntem genellikle DIA SDK'SININ dahili olarak kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasession::findfile](../../debugger/debug-interface-access/idiasession-findfile.md)   
 [Idiasourcefile](../../debugger/debug-interface-access/idiasourcefile.md)