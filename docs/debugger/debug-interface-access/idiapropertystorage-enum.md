---
title: IDiaPropertyStorage::Enum | Microsoft Docs
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
- IDiaPropertyStorage::Enum
ms.assetid: 00e462da-980a-40b3-a2d6-75a25ee809e5
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: d0215656cbe70b5cfd408adf186d5fe6fcc02024
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiapropertystorageenum"></a>IDiaPropertyStorage::Enum
Bu kümesi içinde özellikleri için bir numaralandırıcı alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT Enum (   
   IEnumSTATPROPSTG** ppenum  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppenum`  
 [out] Döndürür bir `IEnumSTATPROPSTG` (Microsoft.VisualStudio.OLE.Interop ad alanında) özellikleri numaralandırması temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)