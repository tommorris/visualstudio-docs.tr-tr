---
title: Idiasession::findfilebyıd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findFileById method
ms.assetid: 710efe04-78b5-4f3e-a1d8-f9b069063503
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 25b034abccc60bcbf6f976930083ad0d90598fae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)