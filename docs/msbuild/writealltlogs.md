---
title: WriteAllTLogs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- WriteAllTLogs
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- WriteAllTLogs
ms.assetid: 1fa3e10b-263c-4960-a9ad-485c02a7a872
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: bc2f4ad277559676f6bc42f080971fbf34ce974a
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="writealltlogs"></a>WriteAllTLogs
İzleme günlükleri tüm iş parçacıkları ve bağlamları yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT WINAPI WriteAllTLogs(LPCTSTR intermediateDirectory, LPCTSTR tlogRootName);  
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
 [WriteContextTLogs](../msbuild/writecontexttlogs.md)