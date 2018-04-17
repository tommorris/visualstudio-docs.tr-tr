---
title: IDiaSymbol::findInlineeLinesByVA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 61427d33-30d2-4ac9-9bd6-c58c6c705072
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4c6f12203f0628fb5ea0a46c35b9019f9be1b58b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolfindinlineelinesbyva"></a>IDiaSymbol::findInlineeLinesByVA
Satır numarası bilgilerini doğrudan veya dolaylı olarak, belirtilen sanal adres (VA) içinde bu simgeyi içermesinden, bulunan tüm işlevlerin yinelemek bir istemci izin veren bir numaralandırmasını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT findInlineeLinesByVA (   
   ULONGLONG             va,  
   DWORD                 length,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `va`  
 [in] VA. adresini belirtir  
  
 `length`  
 [in] Adres aralığı ile bu sorguyu kapsayacak şekilde bayt sayısını belirtir.  
  
 `ppResult`  
 [out] Tutan bir `IDiaEnumLineNumbers` alınır satır numaralarının listesini içeren nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)