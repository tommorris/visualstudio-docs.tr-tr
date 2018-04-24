---
title: IDiaSession::findInlineeLinesByLinenum | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cf32ae7c-a0c8-4800-bc8f-d64fdd15fb06
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0a2b9e1164c1d22e7cbbff1d1c192dd4b7834679
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasessionfindinlineelinesbylinenum"></a>IDiaSession::findInlineeLinesByLinenum
Satır numarası bilgilerini doğrudan veya dolaylı olarak, belirtilen kaynak dosyası ve satır numarası içermesinden, tüm işlevlerin yinelemek bir istemci izin veren bir numaralandırmasını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT findInlineeLinesByVA (   
   IDiaSymbol*           compiland,  
   IDiaSourceFile*       file,  
   DWORD                 linenum,  
   DWORD                 column,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `compiland`  
 [in] Bir [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md) için satır numaralarını aranacağı derlenecek temsil eden nesne. Bu parametre olamaz `NULL`.  
  
 `file`  
 [in] Bir [Idiasourcefile](../../debugger/debug-interface-access/idiasourcefile.md) içinde arama yapmak istediğiniz kaynak dosyasını temsil eden nesne. Bu parametre olamaz `NULL`.  
  
 `linenum`  
 [in] Tabanlı satır numarasını belirtir.  
  
> [!NOTE]
>  Tüm satırları belirtmek için sıfır kullanamazsınız (kullanmak [Idiasession::findlines](../../debugger/debug-interface-access/idiasession-findlines.md) tüm satırları bulmak için yöntem).  
  
 `column`  
 [in] Sütun sayısını belirtir. Tüm sütunları belirtmek için sıfır kullanın. Bir satır halinde bayt uzaklığı bir sütundur.  
  
 `ppResult`  
 [out] Döndürür bir [Idiaenumlinenumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) alındı satır numaralarını listesini içeren nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasourcefile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)