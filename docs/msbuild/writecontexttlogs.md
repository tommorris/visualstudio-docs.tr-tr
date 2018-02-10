---
title: WriteContextTLogs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- WriteContextTLogs
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- WriteContextTLogs
ms.assetid: ffc6c7be-3f22-4624-9ffc-0122fe72b6ec
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5f73d387b8ec0c76f14b4064432a4db068caded7
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="writecontexttlogs"></a>WriteContextTLogs
Geçerli bağlam için günlük dosyalarını yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT WINAPI WriteContextTLogs(LPCTSTR intermediateDirectory, LPCTSTR tlogRootName);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`intermediateDirectory`  
 İzleme günlüğü depolanacağı dizin.  
  
 [in]`tlogRootName`  
 Günlük dosyası adı kök adı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir **HRESULT** ile **başarılı** izleme bağlamı oluşturduysanız biti ayarlanmamış.  
  
## <a name="requirements"></a>Gereksinimler  
 **Header:** FileTracker.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WriteAllTLogs](../msbuild/writealltlogs.md)