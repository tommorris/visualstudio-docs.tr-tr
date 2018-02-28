---
title: IDiaSession::findInlineFramesByAddr | Microsoft Docs
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
ms.assetid: e7dc1ac7-bb09-45be-96d2-365a9b7336e4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 2a05d16e517f15739aeab6c74dbf9c961a3223ad
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasessionfindinlineframesbyaddr"></a>IDiaSession::findInlineFramesByAddr
Tüm satır içi çerçeveler belirli bir adresi üzerinde yinelemek bir istemci izin veren bir numaralandırmasını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT findInlineFramesByAddr (   
   IDiaSymbol*       parent,   DWORD             isect,  
   DWORD             offset,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `parent`  
 [in] Bir `IDiaSymbol` üst temsil eden nesne.  
  
 `isect`  
 [in] Adres bölüm bileşeninin belirtir.  
  
 `offset`  
 [in] Uzaklık bileşeni adresini belirtir.  
  
 `ppResult`  
 [out] Tutan bir `IDiaEnumSymbols` alınır çerçeveler listesini içeren nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)