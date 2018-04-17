---
title: Idiareadexeatoffsetcallback::readexecutableat | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaReadExeAtOffsetCallback::ReadExecutableAt method
ms.assetid: 30b1cef0-b366-4712-8e89-d21f640964f8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e43bb15eb91e3ffdaa7306140206ca80c2547b0b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiareadexeatoffsetcallbackreadexecutableat"></a>IDiaReadExeAtOffsetCallback::ReadExecutableAt
Belirtilen sayıda baytı yürütülebilir bir dosyanın belirtilen uzaklığı başlayarak okur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT ReadExecutableAt (   
   DWORDLONG fileOffset,  
   DWORD     cbData,  
   DWORD*    pcbData,  
   BYTE      data[]  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 fileOffset  
 [in] Okuma başlatmak için yürütülebilir dosyayı uzaklığı.  
  
 cbData  
 [in] Okunacak bayt sayısı.  
  
 pcbData  
 [out] Okunan bayt sayısını döndürür.  
  
 veri]  
 [içinde out] Dosyadan okunan bayt bilgileriyle doldurulan bir dizi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, mutlak dosya uzaklığı kullanarak çalıştırılabilir veri baytı yüklemek için DIA destek kodu tarafından çağrılır. Support, bu yöntem çağrılır [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiareadexeatoffsetcallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)