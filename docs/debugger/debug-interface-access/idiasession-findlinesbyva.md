---
title: Idiasession::findlinesbyva | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findLinesByVA method
ms.assetid: f647eee9-a73c-483b-9fe9-21f42e560a7b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6d9864114820859486ab6b1bfd1700f75496b1f9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiasessionfindlinesbyva"></a>IDiaSession::findLinesByVA
Belirtilen sanal adres (VA) aralığında bulunan satırlar için satır numarası bilgilerini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT findLinesByVA (   
   ULONGLONG             va,  
   DWORD                 length,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `va`  
 [in] VA. adresini belirtir  
  
 `length`  
 [in] Bu sorguyla kapsayacak şekilde adres aralığının bayt sayısını belirtir.  
  
 `ppResult`  
 [out] Döndürür bir [Idiaenumlinenumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) tüm satır listesini içeren nesne belirtilen adres aralığı, kapak numaralandırır.  
  
## <a name="example"></a>Örnek  
 Bu örnek işlevin sanal adres ve uzunluğu kullanarak bir işlevde bulunan tüm satır numaralarını alacağı bir işlev gösterir.  
  
```C++  
IDiaEnumLineNumbers *GetLineNumbersByVA(IDiaSymbol *pFunc, IDiaSession *pSession)  
{  
    IDiaEnumLineNumbers* pEnum = NULL;  
    ULONGLONG            va;  
    ULONGLONG            length;  
  
    if (pFunc->get_virtualAddress ( &va ) == S_OK)  
    {  
        pFunc->get_length( &length );  
        pSession->findLinesByVA( va, static_cast<DWORD>( length ), &pEnum );  
    }  
    return(pEnum);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumlinenumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)