---
title: Idiasession::findfilebyıd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: ed79b65823c3a777c13a90331468074347425ef5
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31466727"
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