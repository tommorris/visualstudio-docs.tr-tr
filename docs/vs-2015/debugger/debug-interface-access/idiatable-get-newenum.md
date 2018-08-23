---
title: Idiatable::get__newenum | Microsoft Docs
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
helpviewer_keywords:
- IDiaTable::get__NewEnum method
ms.assetid: ee89bba8-5d5c-4a0b-aa0d-1aad56baa380
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0de88aeb8f28b31554782ec820790b23722e4c7a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687517"
---
# <a name="idiatablegetnewenum"></a>IDiaTable::get__NewEnum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiatable::get__newenum](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiatable-get-newenum).  
  
Alır <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> bu Numaralandırıcının sürümü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT get__NewEnum (   
   IUnknown** pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Döndürür `IUnknown` temsil eden arabirim <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> bu Numaralandırıcının sürümü.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaTable](../../debugger/debug-interface-access/idiatable.md)



