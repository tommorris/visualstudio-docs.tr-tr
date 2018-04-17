---
title: IDiaSession::findAcceleratorInlineesByLinenum | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 386c87aa-f7b2-4d38-9dd6-fffba9ff01f0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2c5d52dfb474175a3db72325b4739f118d1af0d3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiasessionfindacceleratorinlineesbylinenum"></a>IDiaSession::findAcceleratorInlineesByLinenum
Belirtilen kaynak konumuna karşılık gelen satır içi çerçeveler simgelerini numaralandırması döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT findAcceleratorInlineeLinesByName (   
   IDiaSymbol*           parent,  
   IDiaSourceFile*       file,  
   DWORD                 linenum,  
   DWORD                 colnum,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `parent`  
 [in] Bir `IDiaSymbol` aranması gerekiyor Hızlandırıcı saplama işlevi karşılık gelir.  
  
 `file`  
 [in] `IDiaSourceFile` Kaynak konumun.  
  
 `linenum`  
 [in] Kaynak konumun satır sayısı.  
  
 `colnum`  
 [in] Kaynak konumun sütun sayısı.  
  
 `ppResult`  
 [out] Bir işaretçi bir `IDiaEnumLineNumbers` sonucu ile başlatılmış arabirim işaretçisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiaenumlinenumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)