---
title: Idiaenumsectioncontribs::get__newenum | Microsoft Docs
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
- IDiaEnumSectionContribs::get__NewEnum method
ms.assetid: a16ee92f-3081-416a-98f6-ce6bc8288a8b
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c192a3b91c76d38bc381a6b6ae5da5010eefc64
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687643"
---
# <a name="idiaenumsectioncontribsgetnewenum"></a>IDiaEnumSectionContribs::get__NewEnum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiaenumsectioncontribs::get__newenum](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumsectioncontribs-get-newenum).  
  
Alır <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> bu Numaralandırıcının sürümü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT get__NewEnum (   
   IUnknown** pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pRetVal  
 [out] Döndürür `IUnknown` temsil eden arabirim <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> bu Numaralandırıcının sürümü.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)



