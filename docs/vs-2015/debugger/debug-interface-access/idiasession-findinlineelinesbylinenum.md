---
title: IDiaSession::findInlineeLinesByLinenum | Microsoft Docs
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
ms.assetid: cf32ae7c-a0c8-4800-bc8f-d64fdd15fb06
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2ecd508c98a8a40ea6f89b4d2054326c5794af6a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688531"
---
# <a name="idiasessionfindinlineelinesbylinenum"></a>IDiaSession::findInlineeLinesByLinenum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDiaSession::findInlineeLinesByLinenum](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasession-findinlineelinesbylinenum).  
  
Bir istemci doğrudan veya dolaylı olarak, belirtilen kaynak dosya ve satır numarası, satır içi yapılırlar tüm işlevlerin satır numarası bilgisi yinelemek sağlayan bir sabit listesi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 [in] Bir [Idiasourcefile](../../debugger/debug-interface-access/idiasourcefile.md) içinde arama yapmak istediğiniz kaynak dosyayı temsil eden nesne. Bu parametre olamaz `NULL`.  
  
 `linenum`  
 [in] Bir tane tabanlı satır numarasını belirtir.  
  
> [!NOTE]
>  Tüm satırları belirtmek için sıfır kullanamazsınız (kullanın [Idiasession::findlines](../../debugger/debug-interface-access/idiasession-findlines.md) tüm satırları Bul yöntemi).  
  
 `column`  
 [in] Sütun sayısını belirtir. Sıfır tüm sütunları belirtmek için kullanın. Bir bayt uzaklığı içine satır bir sütundur.  
  
 `ppResult`  
 [out] Döndürür bir [Idiaenumlinenumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) alınan satır numaralarının listesini içeren nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasourcefile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)



