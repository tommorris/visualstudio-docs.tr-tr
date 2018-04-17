---
title: Idiadatasource::get_lasterror | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::get_lastError method
ms.assetid: cf08850b-8b75-4e8c-90bd-bd0214756f99
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9458f287d39dac2a1e8e571aeee3926bdf181823
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiadatasourcegetlasterror"></a>IDiaDataSource::get_lastError
Son yükleme hatası için dosya adını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_lastError (  
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pRetVal  
 [out] Son yük hata ile ilişkili .pdb Dosya adı içeren bir dize döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir yükleme işlemi nedeniyle son hata kodunu döndürür. Döndürür `E_INVALIDARG` varsa `pRetVal` parametresi `NULL`.  
  
## <a name="example"></a>Örnek  
  
```C++  
BSTR    fileName;  
HRESULT errorCode = pSource->get_lastError( &fileName );  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)