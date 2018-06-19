---
title: Idiasession::findsymbolbytoken | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findSymbolByToken method
ms.assetid: 3c92149c-6eef-454f-86be-66e89557b9e6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3f7152a3953475ac2622033101ca739b0b8ee300
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31461330"
---
# <a name="idiasessionfindsymbolbytoken"></a>IDiaSession::findSymbolByToken
Belirtilen meta veri simgesi içeren simge alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT findSymbolByToken (   
   ULONG        token,  
   SymTagEnum   symtag,  
   IDiaSymbol** ppSymbol  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `token`  
 [in] Belirteç belirtir.  
  
 `symtag`  
 [in] Bulunacak simge türü. Değerleri gerçekleştirilecek [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) numaralandırması.  
  
 `ppSymbol`  
 [out] Döndürür bir [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md) simgenin temsil eden nesnesi alınamadı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="example"></a>Örnek  
  
```C++  
IDiaSymbol* pFunc;  
pSession->findSymbolByToken( token, SymTagFunction, &pFunc );  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md)