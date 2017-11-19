---
title: Idiareadexeatoffsetcallback::readexecutableat | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaReadExeAtOffsetCallback::ReadExecutableAt method
ms.assetid: 30b1cef0-b366-4712-8e89-d21f640964f8
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8cb9ff60968d806cfdee0201746a02483895b0af
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)