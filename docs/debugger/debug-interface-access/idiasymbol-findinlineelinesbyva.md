---
title: IDiaSymbol::findInlineeLinesByVA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 61427d33-30d2-4ac9-9bd6-c58c6c705072
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6fd0167eaea86b13c8d197d39c6042f5ad183fcd
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31464394"
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