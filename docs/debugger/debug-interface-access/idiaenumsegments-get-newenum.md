---
title: Idiaenumsegments::get__newenum | Microsoft Docs
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
helpviewer_keywords:
- IDiaEnumSegments::get__NewEnum method
ms.assetid: 504505fa-b35c-402f-a440-8972c589cc5b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 98b2dc988fdbf56af6a003e01a7e4423d31ba42a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiaenumsegmentsgetnewenum"></a>IDiaEnumSegments::get__NewEnum
Alır <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> bu Sıralayıcı sürümü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get__NewEnum (   
   IUnknown** pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pRetVal  
 [out] Döndürür `IUnknown` temsil eden arabirim <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> bu Sıralayıcı sürümü.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)